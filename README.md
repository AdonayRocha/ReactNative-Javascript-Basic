# ReactNative - Javascript-Basic - Anotações 📚

Este repositório contém anotações e exemplos básicos sobre React Native, abordando desde a criação de um projeto até o uso de componentes, props, estados e estilos. Essas anotações foram feitas durante as aulas da faculdade e são úteis para quem está começando com React Native.

---

## Criando um projeto React Native Default [Blank]

Para iniciar um projeto React Native, siga os passos abaixo:

### 1. Criar um novo projeto

```bash
npx create-expo-app@latest -t
```
Esse comando cria um novo projeto React Native com uma estrutura básica e utiliza o "-t" para encontrar a ultima versão.

### 2. Acessar a pasta do projeto

```bash
cd {nome_do_projeto}
```
Substitua `{nome_do_projeto}` pelo nome do seu projeto. Isso navega até a pasta do projeto.

### 3. Abrir o projeto no VSCode

```bash
code .
```
Esse comando abre a pasta do projeto diretamente no Visual Studio Code.

### 4. Iniciar o servidor de desenvolvimento

```bash
npm start
```
Isso inicia o servidor de desenvolvimento do React Native, permitindo que você visualize o app no seu emulador [Geralmente Android Studio] ou dispositivo físico.

---

## ReactNative 🧩 
### Estrutura Básica de um Componente 

No React Native, tudo é construído em torno de componentes, assim como no React.js. Abaixo está um exemplo básico de um componente funcional:

```javascript
import React from 'react';
import { View, Text } from 'react-native';

export function Clock(props) {
  return (
    <View>
      <Text>{props.time}</Text>
    </View>
  );
}
```

---

## Hooks: useState e useEffect 🏗️

Hooks são funções que permitem usar estado e outros recursos do React em componentes funcionais. Os mais comuns são `useState` e `useEffect`.

### useState
O `useState` permite adicionar estado ao seu componente. Exemplo:

```javascript
import React, { useState } from 'react';
import { View, Text, Button } from 'react-native';

export function Counter() {
  const [count, setCount] = useState(0);

  return (
    <View>
      <Text>Contador: {count}</Text>
      <Button title="Incrementar" onPress={() => setCount(count + 1)} />
    </View>
  );
}
```

### useEffect
O `useEffect` executa efeitos colaterais, como chamadas de API ou atualizações do DOM. Ele recebe um array de dependências que determina quando o efeito deve ser executado.

```javascript
import React, { useState, useEffect } from 'react';
import { View, Text } from 'react-native';

export function Timer() {
  const [time, setTime] = useState(0);

  useEffect(() => {
    const interval = setInterval(() => {
      setTime(time + 1);
    }, 1000);

    return () => clearInterval(interval); // Limpa o intervalo ao desmontar o componente
  }, [time]);

  return (
    <View>
      <Text>Tempo: {time} segundos</Text>
    </View>
  );
}
```

## Explicação 🔍
- **StyleSheet.create**: Cria um objeto de estilos que pode ser reutilizado.
- **flex: 1**: Faz com que o container ocupe todo o espaço disponível.
- **justifyContent** e **alignItems**: Alinham os itens vertical e horizontalmente.
- **props**: São propriedades passadas para o componente. No exemplo acima, `props.time` é uma propriedade que exibe o tempo.
- **View**: É um container que agrupa elementos. Sempre use uma `View` para envolver outros componentes. Também é um identificador do reactNative.
- **Text**: Função texto na tela.

---

## Dicas Importantes 📌

- **Sempre use View para pequenos projetos**: Para projetos simples, uma `View` é suficiente para agrupar componentes.
- **Use ListView ou FlatList para projetos grandes**: Quando há muitos itens para renderizar, como listas, prefira `FlatList` para melhor desempenho.

---

## Recursos Adicionais 📚

- [Documentação Oficial do React Native](https://reactnative.dev/docs/getting-started)
- [Expo Documentation](https://docs.expo.dev/)
- [React Hooks Guide](https://reactjs.org/docs/hooks-intro.html)
