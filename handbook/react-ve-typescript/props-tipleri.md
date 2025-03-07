# Props Tipleri

React projelerimizde propların tiplerini tanımlamak için farklı yöntemler vardır.  Örneğin aşağıdaki gibi propların tipini direk tip objesiyle tanımlayabiliriz.

```typescript
type PropTypes = {
    children?: JSX.Element
    name?: 'ahmet' | "fatih";
    surname?: string;
    key?: string
}

const Character = (props: CharacterPropTypes) => {
    const {name, surname, children} = props;
    return (
        <div>
            <h1>{`${name} ${surname}`}</h1>
            {children}
        </div>
    );
};
```

 Bu tanımlamanın en büyük handikapı children ve key için de tip tanımlaması yapmamız gerekmektedir. 

Alternatif olarak ve sıklıkla aşağıdaki kullanım ile tip tanımlaması yapılmaktadır. **React.FC** yerine **FC** veye **FunctionComponent** tanımlamaları da yapılabilir.

```typescript
const Character:React.FC<CharacterPropTypes> = (props) => {
    const {name, surname, children} = props;
    return (
        <div>
            <h1>{`${name} ${surname}`}</h1>
            {children}
        </div>
    );
};
```

 Bu şekilde tip tanımlaması yaptığımızda, children için tip tanımlaması yapmamıza gerek yoktur.

