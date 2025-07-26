

### **`let` (Mutável)**

  * **Reassignável:** Uma variável declarada com `let` pode ter seu valor **alterado (reassignado)** a qualquer momento após sua declaração inicial.
  * **Escopo de Bloco:** A variável só existe e pode ser acessada dentro do bloco de código (delimitado por chaves `{}`) onde foi definida.

**Exemplo com `let`:**

```javascript
let contador = 0; // Declara e inicializa
console.log(contador); // Saída: 0

contador = 1; // Reassigna o valor de 'contador'
console.log(contador); // Saída: 1

if (true) {
  let mensagem = "Olá"; // 'mensagem' existe apenas dentro deste bloco
  console.log(mensagem); // Saída: Olá
}
// console.log(mensagem); // Erro: 'mensagem' não está definida aqui
```

-----

### **`const` (Imutável para Reassignação)**

  * **Não Reassignável:** Uma variável declarada com `const` **não pode ter seu valor reassignado** após a declaração inicial. Você precisa inicializá-la no momento da declaração.
  * **Escopo de Bloco:** Assim como `let`, a variável declarada com `const` também tem escopo de bloco.

**Exemplo com `const`:**

```javascript
const PI = 3.14159; // Declara e inicializa uma constante
console.log(PI); // Saída: 3.14159

// PI = 3.14; // ERRO! Não é possível reassignar uma constante
// console.log(PI);

const nomeCompleto = "João Silva";
console.log(nomeCompleto); // Saída: João Silva

// const semValor; // ERRO! 'const' precisa ser inicializada na declaração
```

-----

### **Uma observação importante sobre `const` e objetos/arrays:**

Embora você não possa reassignar uma variável `const`, isso **não significa que o conteúdo de um objeto ou array declarado com `const` seja imutável**. Você pode modificar as propriedades de um objeto ou os elementos de um array, mas não pode reassignar o objeto/array inteiro a uma nova referência.

**Exemplo:**

```javascript
const pessoa = {
  nome: "Ana",
  idade: 25
};

console.log(pessoa); // Saída: { nome: 'Ana', idade: 25 }

pessoa.idade = 26; // Isso é permitido! Você está modificando uma propriedade do objeto.
console.log(pessoa); // Saída: { nome: 'Ana', idade: 26 }

// pessoa = { nome: 'Carlos', idade: 30 }; // ERRO! Não pode reassignar o objeto 'pessoa'.

const frutas = ["maçã", "banana"];
console.log(frutas); // Saída: [ 'maçã', 'banana' ]

frutas.push("laranja"); // Isso é permitido! Você está adicionando um elemento ao array.
console.log(frutas); // Saída: [ 'maçã', 'banana', 'laranja' ]

// frutas = ["uva", "kiwi"]; // ERRO! Não pode reassignar o array 'frutas'.
```

-----

### **Quando usar cada um?**

  * Use **`const`** por padrão: Se o valor de uma variável não precisa mudar após sua inicialização, `const` é a melhor escolha. Isso torna seu código mais seguro e mais fácil de entender, pois você sabe que aquele valor não será alterado inesperadamente.
  * Use **`let`** quando souber que o valor mudará: Se você precisar reassignar o valor de uma variável (como em contadores de loops, variáveis que armazenam estados que mudam, etc.), então `let` é a escolha correta.

Em resumo, a principal distinção é a **capacidade de reassignação**: `let` permite, `const` não permite. Ambos oferecem **escopo de bloco**, o que é uma melhoria em relação ao antigo `var` (que tem escopo de função).
