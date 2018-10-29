<!-- 基础用法 -->
<template>
    <Tree :data="data1"></Tree>
</template>
<script>
    export default {
        data () {
            return {
                data1: [
                    {
                        title: 'parent 1',
                        expand: true,
                        children: [
                            {
                                title: 'parent 1-1',
                                expand: true,
                                children: [
                                    {
                                        title: 'leaf 1-1-1'
                                    },
                                    {
                                        title: 'leaf 1-1-2'
                                    }
                                ]
                            },
                            {
                                title: 'parent 1-2',
                                expand: true,
                                children: [
                                    {
                                        title: 'leaf 1-2-1'
                                    },
                                    {
                                        title: 'leaf 1-2-1'
                                    }
                                ]
                            }
                        ]
                    }
                ]
            }
        }
    }
</script>

<!-- 默认展开、选中、勾选和禁用 -->
<template>
    <Tree :data="data4" show-checkbox multiple></Tree>
</template>
<script>
    export default {
        data () {
            return {
                data4: [
                    {
                        title: 'parent 1',
                        expand: true,
                        selected: true,
                        children: [
                            {
                                title: 'parent 1-1',
                                expand: true,
                                children: [
                                    {
                                        title: 'leaf 1-1-1',
                                        disabled: true
                                    },
                                    {
                                        title: 'leaf 1-1-2'
                                    }
                                ]
                            },
                            {
                                title: 'parent 1-2',
                                expand: true,
                                children: [
                                    {
                                        title: 'leaf 1-2-1',
                                        checked: true
                                    },
                                    {
                                        title: 'leaf 1-2-1'
                                    }
                                ]
                            }
                        ]
                    }
                ]
            }
        }
    }
</script>

<!-- 自定义节点内容 -->
<template>
    <Tree :data="data5" :render="renderContent"></Tree>
</template>
<script>
export default {
    data() {
        return {
            data5: [
                {
                    title: "parent 1",
                    expand: true,
                    render: (h, { root, node, data }) => {
                        return h(
                            "span",
                            {
                                style: {
                                    display: "inline-block",
                                    width: "32px"
                                }
                            },
                            [
                                h(
                                    "span",
                                    {
                                        style: {
                                            display: "inline-block",
                                            width: "32px"
                                        }
                                    },
                                    [
                                        h("Icon", {
                                            props: {
                                                type: "ios-folder-outline"
                                            }
                                        }),
                                        h(
                                            "span",
                                            {
                                                style: {
                                                    display: "inline-block",
                                                    width: "32px",
                                                    float: "right"
                                                }
                                            },
                                            data.title
                                        )
                                    ]
                                ),
                                h(
                                    "span",
                                    {
                                        style: {
                                            display: "inline-block",
                                            width: "32px"
                                        }
                                    },
                                    [
                                        h("Button", {
                                            props: Object.assign(
                                                {},
                                                this.buttonProps,
                                                {
                                                    icon: "ios-add",
                                                    type: "primary"
                                                }
                                            ),
                                            on: {
                                                click: () => {
                                                    this.append(data);
                                                }
                                            }
                                        })
                                    ]
                                )
                            ]
                        );
                    },
                    children: [
                        {
                            title: "child 1-1",
                            expand: true,
                            children: [
                                {
                                    title: "leaf 1-1-1",
                                    expand: true
                                },
                                {
                                    title: "leaf 1-1-2",
                                    expand: true
                                }
                            ]
                        },
                        {
                            title: "child 1-2",
                            expand: true,
                            children: [
                                {
                                    title: "leaf 1-2-1",
                                    expand: true
                                },
                                {
                                    title: "leaf 1-2-1",
                                    expand: true
                                }
                            ]
                        }
                    ]
                }
            ],
            buttonProps: {
                type: "default",
                size: "small"
            }
        };
    },
    methods: {
        renderContent(h, { root, node, data }) {
            return h(
                "span",
                {
                    style: {
                        display: "inline-block",
                        width: "32px"
                    }
                },
                [
                    h(
                        "span",
                        {
                            style: {
                                display: "inline-block",
                                width: "32px"
                            }
                        },
                        [
                            h("Icon", {
                                props: {
                                    type: "ios-paper-outline"
                                }
                            }),
                            h(
                                "span",
                                {
                                    style: {
                                        display: "inline-block",
                                        width: "32px",
                                        float: "right"
                                    }
                                },
                                data.title
                            )
                        ]
                    ),
                    h(
                        "span",
                        {
                            style: {
                                display: "inline-block",
                                width: "32px"
                            }
                        },
                        [
                            h("Button", {
                                props: Object.assign({}, this.buttonProps, {
                                    icon: "ios-add"
                                }),
                                style: {
                                    marginBottom: "8px"
                                },
                                on: {
                                    click: () => {
                                        this.append(data);
                                    }
                                }
                            }),
                            h("Button", {
                                props: Object.assign({}, this.buttonProps, {
                                    icon: "ios-remove"
                                }),
                                on: {
                                    click: () => {
                                        this.remove(root, node, data);
                                    }
                                }
                            })
                        ]
                    )
                ]
            );
        },
        append(data) {
            const children = data.children || [];
            children.push({
                title: "appended node",
                expand: true
            });
            this.$set(data, "children", children);
        },
        remove(root, node, data) {
            const parentKey = root.find(el => el === node).parent;
            const parent = root.find(el => el.nodeKey === parentKey).node;
            const index = parent.children.indexOf(data);
            parent.children.splice(index, 1);
        }
    }
};
</script>