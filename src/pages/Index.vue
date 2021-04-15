<template>
  <q-page class="q-pa-sm">
     <q-card class="bg-transparent no-shadow no-border">
        <q-card-section class="q-pa-none">
          <div class="row q-col-gutter-sm ">
            
            <div class="col-md-4 col-sm-12 col-xs-12">
              
    <Cascader
      ref="wt"
      label="部门"
      :options="deptsOption"
      optlabel="name"
      optvalue="id"
      :selected="selected"
      @change="handleDeptIdChange"
    ></Cascader>
            </div>
            <div class="col-md-2 col-sm-12 col-xs-12">
              
    <div>你选择的是：{{ selectedvalue }}</div>
            </div>
          </div>
        </q-card-section>
      </q-card>
  </q-page>
</template>

<script>
const data = [
  {
    id: 12,
    name: "成都铁路局",
    parentId: 1,
    deptType: 2,
    children: [
      {
        id: 63,
        name: "成都机务段",
        parentId: 12,
        deptType: 3,
        children: [
          {
            id: 87,
            name: "东部指挥所",
            parentId: 63,
            deptType: 4,
            children: [
              { id: 111, name: "三岔湖指挥站", parentId: 87, deptType: 5 },
              { id: 114, name: "东部指挥所", parentId: 87, deptType: 5 }
            ],
            childList: [
              { id: 111, name: "三岔湖指挥站", parentId: 87, deptType: 5 },
              { id: 114, name: "东部指挥所", parentId: 87, deptType: 5 }
            ]
          },
          {
            id: 104,
            name: "天府新区站",
            parentId: 63,
            deptType: 4,
            children: [
              { id: 116, name: "天府新区万安", parentId: 104, deptType: 5 },
              {
                id: 117,
                name: "天府新区站麓山站",
                parentId: 104,
                deptType: 5,
                children: [
                  {
                    id: 118,
                    name: "麓山一",
                    parentId: 117,
                    deptType: 6,
                    children: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ],
                    childList: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ]
                  }
                ],
                childList: [
                  {
                    id: 118,
                    name: "麓山一",
                    parentId: 117,
                    deptType: 6,
                    children: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ],
                    childList: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ]
                  }
                ]
              }
            ],
            childList: [
              { id: 116, name: "天府新区万安", parentId: 104, deptType: 5 },
              {
                id: 117,
                name: "天府新区站麓山站",
                parentId: 104,
                deptType: 5,
                children: [
                  {
                    id: 118,
                    name: "麓山一",
                    parentId: 117,
                    deptType: 6,
                    children: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ],
                    childList: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ]
                  }
                ],
                childList: [
                  {
                    id: 118,
                    name: "麓山一",
                    parentId: 117,
                    deptType: 6,
                    children: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ],
                    childList: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ]
                  }
                ]
              }
            ]
          },
          { id: 105, name: "4353", parentId: 63, deptType: 4 },
          { id: 107, name: "3453", parentId: 63, deptType: 4 },
          { id: 110, name: "企鹅", parentId: 63, deptType: 4 },
          { id: 115, name: "双流", parentId: 63, deptType: 4 }
        ],
        childList: [
          {
            id: 87,
            name: "东部指挥所",
            parentId: 63,
            deptType: 4,
            children: [
              { id: 111, name: "三岔湖指挥站", parentId: 87, deptType: 5 },
              { id: 114, name: "东部指挥所", parentId: 87, deptType: 5 }
            ],
            childList: [
              { id: 111, name: "三岔湖指挥站", parentId: 87, deptType: 5 },
              { id: 114, name: "东部指挥所", parentId: 87, deptType: 5 }
            ]
          },
          {
            id: 104,
            name: "天府新区站",
            parentId: 63,
            deptType: 4,
            children: [
              { id: 116, name: "天府新区万安", parentId: 104, deptType: 5 },
              {
                id: 117,
                name: "天府新区站麓山站",
                parentId: 104,
                deptType: 5,
                children: [
                  {
                    id: 118,
                    name: "麓山一",
                    parentId: 117,
                    deptType: 6,
                    children: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ],
                    childList: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ]
                  }
                ],
                childList: [
                  {
                    id: 118,
                    name: "麓山一",
                    parentId: 117,
                    deptType: 6,
                    children: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ],
                    childList: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ]
                  }
                ]
              }
            ],
            childList: [
              { id: 116, name: "天府新区万安", parentId: 104, deptType: 5 },
              {
                id: 117,
                name: "天府新区站麓山站",
                parentId: 104,
                deptType: 5,
                children: [
                  {
                    id: 118,
                    name: "麓山一",
                    parentId: 117,
                    deptType: 6,
                    children: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ],
                    childList: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ]
                  }
                ],
                childList: [
                  {
                    id: 118,
                    name: "麓山一",
                    parentId: 117,
                    deptType: 6,
                    children: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ],
                    childList: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ]
                  }
                ]
              }
            ]
          },
          { id: 105, name: "4353", parentId: 63, deptType: 4 },
          { id: 107, name: "3453", parentId: 63, deptType: 4 },
          { id: 110, name: "企鹅", parentId: 63, deptType: 4 },
          { id: 115, name: "双流", parentId: 63, deptType: 4 }
        ]
      },
      {
        id: 64,
        name: "重庆机务段",
        parentId: 12,
        deptType: 3,
        children: [
          { id: 108, name: "渝北指挥站", parentId: 64, deptType: 4 },
          { id: 109, name: "杨家坪指挥站", parentId: 64, deptType: 4 },
          { id: 113, name: "九龙坡指挥站", parentId: 64, deptType: 4 }
        ],
        childList: [
          { id: 108, name: "渝北指挥站", parentId: 64, deptType: 4 },
          { id: 109, name: "杨家坪指挥站", parentId: 64, deptType: 4 },
          { id: 113, name: "九龙坡指挥站", parentId: 64, deptType: 4 }
        ]
      },
      {
        id: 65,
        name: "贵阳机务段",
        parentId: 12,
        deptType: 3,
        children: [
          { id: 85, name: "贵阳机务段445", parentId: 65, deptType: 4 }
        ],
        childList: [
          { id: 85, name: "贵阳机务段445", parentId: 65, deptType: 4 }
        ]
      },
      { id: 66, name: "西昌机务段", parentId: 12, deptType: 3 }
    ],
    childList: [
      {
        id: 63,
        name: "成都机务段",
        parentId: 12,
        deptType: 3,
        children: [
          {
            id: 87,
            name: "东部指挥所",
            parentId: 63,
            deptType: 4,
            children: [
              { id: 111, name: "三岔湖指挥站", parentId: 87, deptType: 5 },
              { id: 114, name: "东部指挥所", parentId: 87, deptType: 5 }
            ],
            childList: [
              { id: 111, name: "三岔湖指挥站", parentId: 87, deptType: 5 },
              { id: 114, name: "东部指挥所", parentId: 87, deptType: 5 }
            ]
          },
          {
            id: 104,
            name: "天府新区站",
            parentId: 63,
            deptType: 4,
            children: [
              { id: 116, name: "天府新区万安", parentId: 104, deptType: 5 },
              {
                id: 117,
                name: "天府新区站麓山站",
                parentId: 104,
                deptType: 5,
                children: [
                  {
                    id: 118,
                    name: "麓山一",
                    parentId: 117,
                    deptType: 6,
                    children: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ],
                    childList: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ]
                  }
                ],
                childList: [
                  {
                    id: 118,
                    name: "麓山一",
                    parentId: 117,
                    deptType: 6,
                    children: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ],
                    childList: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ]
                  }
                ]
              }
            ],
            childList: [
              { id: 116, name: "天府新区万安", parentId: 104, deptType: 5 },
              {
                id: 117,
                name: "天府新区站麓山站",
                parentId: 104,
                deptType: 5,
                children: [
                  {
                    id: 118,
                    name: "麓山一",
                    parentId: 117,
                    deptType: 6,
                    children: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ],
                    childList: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ]
                  }
                ],
                childList: [
                  {
                    id: 118,
                    name: "麓山一",
                    parentId: 117,
                    deptType: 6,
                    children: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ],
                    childList: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ]
                  }
                ]
              }
            ]
          },
          { id: 105, name: "4353", parentId: 63, deptType: 4 },
          { id: 107, name: "3453", parentId: 63, deptType: 4 },
          { id: 110, name: "企鹅", parentId: 63, deptType: 4 },
          { id: 115, name: "双流", parentId: 63, deptType: 4 }
        ],
        childList: [
          {
            id: 87,
            name: "东部指挥所",
            parentId: 63,
            deptType: 4,
            children: [
              { id: 111, name: "三岔湖指挥站", parentId: 87, deptType: 5 },
              { id: 114, name: "东部指挥所", parentId: 87, deptType: 5 }
            ],
            childList: [
              { id: 111, name: "三岔湖指挥站", parentId: 87, deptType: 5 },
              { id: 114, name: "东部指挥所", parentId: 87, deptType: 5 }
            ]
          },
          {
            id: 104,
            name: "天府新区站",
            parentId: 63,
            deptType: 4,
            children: [
              { id: 116, name: "天府新区万安", parentId: 104, deptType: 5 },
              {
                id: 117,
                name: "天府新区站麓山站",
                parentId: 104,
                deptType: 5,
                children: [
                  {
                    id: 118,
                    name: "麓山一",
                    parentId: 117,
                    deptType: 6,
                    children: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ],
                    childList: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ]
                  }
                ],
                childList: [
                  {
                    id: 118,
                    name: "麓山一",
                    parentId: 117,
                    deptType: 6,
                    children: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ],
                    childList: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ]
                  }
                ]
              }
            ],
            childList: [
              { id: 116, name: "天府新区万安", parentId: 104, deptType: 5 },
              {
                id: 117,
                name: "天府新区站麓山站",
                parentId: 104,
                deptType: 5,
                children: [
                  {
                    id: 118,
                    name: "麓山一",
                    parentId: 117,
                    deptType: 6,
                    children: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ],
                    childList: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ]
                  }
                ],
                childList: [
                  {
                    id: 118,
                    name: "麓山一",
                    parentId: 117,
                    deptType: 6,
                    children: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ],
                    childList: [
                      {
                        id: 119,
                        name: "麓山1-1",
                        parentId: 118,
                        deptType: 7,
                        children: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ],
                        childList: [
                          {
                            id: 120,
                            name: "麓山1-1-1",
                            parentId: 119,
                            deptType: 8
                          }
                        ]
                      }
                    ]
                  }
                ]
              }
            ]
          },
          { id: 105, name: "4353", parentId: 63, deptType: 4 },
          { id: 107, name: "3453", parentId: 63, deptType: 4 },
          { id: 110, name: "企鹅", parentId: 63, deptType: 4 },
          { id: 115, name: "双流", parentId: 63, deptType: 4 }
        ]
      },
      {
        id: 64,
        name: "重庆机务段",
        parentId: 12,
        deptType: 3,
        children: [
          { id: 108, name: "渝北指挥站", parentId: 64, deptType: 4 },
          { id: 109, name: "杨家坪指挥站", parentId: 64, deptType: 4 },
          { id: 113, name: "九龙坡指挥站", parentId: 64, deptType: 4 }
        ],
        childList: [
          { id: 108, name: "渝北指挥站", parentId: 64, deptType: 4 },
          { id: 109, name: "杨家坪指挥站", parentId: 64, deptType: 4 },
          { id: 113, name: "九龙坡指挥站", parentId: 64, deptType: 4 }
        ]
      },
      {
        id: 65,
        name: "贵阳机务段",
        parentId: 12,
        deptType: 3,
        children: [
          { id: 85, name: "贵阳机务段445", parentId: 65, deptType: 4 }
        ],
        childList: [
          { id: 85, name: "贵阳机务段445", parentId: 65, deptType: 4 }
        ]
      },
      { id: 66, name: "西昌机务段", parentId: 12, deptType: 3 }
    ]
  }
];

import Cascader from "../components/Cascader";
export default {
  name: "PageIndex",

  components: { Cascader },
  data() {
    return {
      deptsOption: [],
      selected: null,
      selectedvalue: null
    };
  },
  mounted(){
    setTimeout(() => {
      this.deptsOption = data
      this.selected = 63
    }, 200);
  },
  methods: {
    handleDeptIdChange(v) {
      if (v) {
        this.selectedvalue = v;
      } else {
        this.selectedvalue = null;
      }
    }
  }
};
</script>
