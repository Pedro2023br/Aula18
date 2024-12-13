

## Projeto: Exercícios com React Hooks

Este projeto foi criado para praticar o uso de **React Hooks** como `useState` em três componentes: `Contador`, `BotaoAlternador` e `ListaDeTarefas`.

## **Componentes Criados**

### 1. **Contador**
#### **Descrição**
O componente `Contador` implementa um contador simples que permite incrementar e decrementar o número exibido na tela. Ele utiliza o **hook `useState`** para gerenciar o estado do número.

#### **Blocos de Código e Explicações**

1. **Estado Inicial**
   ```javascript
   const [numero, setNumero] = useState(0);
   ```
   - `numero`: Representa o valor atual do contador.
   - `setNumero`: Função para atualizar o valor de `numero`.
   - Inicializamos o estado com `0`.

2. **Botões de Incremento e Decremento**
   ```javascript
   <button onClick={() => setNumero(numero + 1)}>+1</button>
   <button onClick={() => numero > 0 && setNumero(numero - 1)}>-1</button>
   ```
   - Botão de incremento (`+1`): Incrementa o valor de `numero` ao ser clicado.
   - Botão de decremento (`-1`): Decrementa o valor apenas se `numero` for maior que `0`.

---

### 2. **BotaoAlternador**
#### **Descrição**
O componente `BotaoAlternador` implementa um botão que alterna entre os estados `"Ligado"` e `"Desligado"`. Cada estado é exibido com uma cor diferente, utilizando CSS dinâmico.

#### **Blocos de Código e Explicações**

1. **Estado Inicial**
   ```javascript
   const [estado, setEstado] = useState("Desligado");
   ```
   - `estado`: Indica se o botão está "Ligado" ou "Desligado".
   - `setEstado`: Função para alternar o valor do estado.

2. **Função de Alternância**
   ```javascript
   const alternarEstado = () => {
     setEstado(estado === "Ligado" ? "Desligado" : "Ligado");
   };
   ```
   - Verifica o estado atual e alterna para o outro estado.

3. **Estilo Dinâmico**
   ```javascript
   <button className={estado === "Ligado" ? "ligado" : "desligado"}>
     {estado}
   </button>
   ```
   - Aplica classes CSS diferentes dependendo do estado.

4. **CSS**
   ```css
   .ligado {
     background-color: green;
     color: white;
   }
   .desligado {
     background-color: red;
     color: white;
   }
   ```
   - Define cores para os estados "Ligado" (verde) e "Desligado" (vermelho).

---

### 3. **ListaDeTarefas**
#### **Descrição**
O componente `ListaDeTarefas` implementa uma lista onde o usuário pode adicionar tarefas e removê-las ao clicar nelas. Ele utiliza o **hook `useState`** para gerenciar a lista de tarefas e o texto do campo de entrada.

#### **Blocos de Código e Explicações**

1. **Estados Iniciais**
   ```javascript
   const [tarefa, setTarefa] = useState("");
   const [tarefas, setTarefas] = useState([]);
   ```
   - `tarefa`: Armazena o texto digitado no campo de entrada.
   - `tarefas`: Array que contém as tarefas adicionadas.

2. **Adicionar Tarefa**
   ```javascript
   const adicionarTarefa = () => {
     if (tarefa.trim() !== "") {
       setTarefas([...tarefas, tarefa]);
       setTarefa("");
     }
   };
   ```
   - Verifica se o texto não está vazio.
   - Adiciona o texto ao array `tarefas` e limpa o campo de entrada.

3. **Remover Tarefa**
   ```javascript
   const removerTarefa = (index) => {
     setTarefas(tarefas.filter((_, i) => i !== index));
   };
   ```
   - Remove a tarefa clicada da lista.

4. **Renderizar Lista**
   ```javascript
   <ul>
     {tarefas.map((item, index) => (
       <li key={index} onClick={() => removerTarefa(index)}>
         {item}
       </li>
     ))}
   </ul>
   ```
   - Mapeia o array `tarefas` para renderizar cada tarefa como um item da lista.
   - Permite remover uma tarefa clicando nela.
```

Se precisar que eu gere esse conteúdo em um arquivo `.md`, envie um comando ou solicite o upload! 😊
