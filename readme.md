# minecraft schema example

## 简介

## 规则

### 接口规范


``` typescript
type NbtNumberType = 'byte' | 'int' | 'short' | 'double' | 'long' | 'float' | 'number
type NbtBoolType = 'bool'
type NbtStringType = 'string'
type NbtListType = 'list'
type NbtEnumType = 'enum'
type NbtObjectType = 'object'
type NbtType = NbtNumberType | NbtBoolType | NbtStringType | NbtListType | NbtEnumType | NbtObjectType

interface GObject<T> { [propName: string]: T; }
interface ISelect { id: string; name: string; }

type NbtObject = GObject<NbtProps>

interface NbtComponent {
    base?: string[]; // 模板
    has?: string[] | boolean; // 已选择的项
    nbt?: NbtObject; // nbt定义
    root?: boolean; // 是否为根类型
}
interface NbtProps {
    type?: NbtType; // 类型
    enum?: string | ISelect; // 下拉框的枚举值
    subtype?: string | string[]; // 子类型
    default?: string | boolean | number; // 默认值
    title?: string; // 标题
    description?: string; // 备注
    disabled?: boolean; // 禁用
    link?: string[]; // 链接
    linkType?: string; // 链接类型
    
    minItems?: number; // 将来特性
    maxItems?: number; // 将来特性
    max?: number; // 将来特性
    min?: number; // 将来特性
}
```