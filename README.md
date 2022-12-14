<h1 align="center">Meu Primeiro ToDoList React Native</h1>
<p align="center">Um pouco sobre meu projeto</p>

#  Telas e Funções

### Inicio

<img src="https://github.com/devfelipenunes/ToDoListReactNative/blob/main/readme/1.jpg" width="400" height="790">

> primeira tela do app, não foquei tanto no layout mas sim nas funcionalidades.

### Primeira anotação

<img src="https://github.com/devfelipenunes/ToDoListReactNative/blob/main/readme/2.jpg" width="400" height="790">

> Como todo ToDoList temos a função de adicionar.

```
async function addTask(){
    if(newTask === ''){
      return
    }

    const search = task.filter(task => task === newTask)

    if(search.length !== 0){
      Alert.alert('Atenção', 'Nome da tarefa repetido!')
      return
    }

    setTask([...task, newTask])
    setNewTask('')
    Keyboard.dismiss()
  }

```

### Verificando repetição

<img src="https://github.com/devfelipenunes/ToDoListReactNative/blob/main/readme/3.jpg" width="400" height="790">

> Para que não ocorra erros futuros, prefirir por introduzir uma função de verificação de repetição de tarefas na função AddTask().

```
const search = task.filter(task => task === newTask)

    if(search.length !== 0){
      Alert.alert('Atenção', 'Nome da tarefa repetido!')
      return
    }
```

### Excluindo dados

<img src="https://github.com/devfelipenunes/ToDoListReactNative/blob/main/readme/4.jpg" width="400" height="790">

> Assim que ficou minha função de Excluir dados.

```
async function removeTask(item){
    Alert.alert(
      "Deletar Task",
      "Tem certeza de deseja remover esta anotação?",
      [
        {
          text: 'Cancel',
          onPress: () => {

          },
          style: 'cancel'
        },{
          text: "Ok",
          onPress: ()=> setTask(task.filter(tasks => tasks !== item))
        }
      ],
      {cancelable: false}
    )
  }

```
