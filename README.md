
# Projeto de Desenvolvimento para Aplicações Móveis

Este projeto tem como objetivo o desenvolvimento de uma aplicação móvel para dispositivos Android, utilizando a linguagem Kotlin como base para sua construção. O propósito deste aplicativo é viabilizar o agendamento de cortes de cabelo de forma eficiente.A aplicação proporcionará um login individualizado para diferentes barbearias, garantindo acesso exclusivo e personalizado à plataforma. Além disso, a aplicação permitirá listar os barbeiros disponíveis, oferecendo informações detalhadas sobre suas especialidades e disponibilidade de horários.

O processo de agendamento será simplificado e personalizado, possibilitando aos clientes escolherem entre diferentes opções, como cortar a barba, cortar o cabelo, ou ambas as opções.
Adicionalmente, a aplicação permitirá a remoção de barbeiros da lista de disponíveis, bem como a flexibilidade de cancelar ou remarcar horários, de acordo com prazos estabelecidos.

Este projeto visa proporcionar uma solução eficaz e conveniente para o agendamento de serviços de barbearia, visando melhorar a experiência do cliente e facilitar a gestão das atividades das barbearias envolvidas.

## Nome da Equipe
devmob


## 🚀 Integrantes da Equipe 

- Cauet Roberto
- Roberto Luís
- Júlio César
- Victor Hugo
- Pedro Vínicius Soares Cavalcante
- Patrick Kluivert
- Matheus Estevam de Oliveira


## API
Para a implementação deste projeto, será utilizado o [Firebase](https://firebase.google.com/?gad=1&gclid=CjwKCAjw9-6oBhBaEiwAHv1QvLedly1LZD4fsCi1DU-kGTsvNkcEaibP2_1kO2QYvSq6tWrrXi1pzRoCjS0QAvD_BwE&gclsrc=aw.ds) como sistema de gerenciamento de banco de dados, visando estabelecer uma base sólida para o armazenamento e recuperação de informações cruciais. O [Firebase](https://firebase.google.com/?gad=1&gclid=CjwKCAjw9-6oBhBaEiwAHv1QvLedly1LZD4fsCi1DU-kGTsvNkcEaibP2_1kO2QYvSq6tWrrXi1pzRoCjS0QAvD_BwE&gclsrc=aw.ds), uma plataforma de desenvolvimento móvel fornecida pelo Google, oferece uma infraestrutura confiável e escalável para nossas necessidades de armazenamento de dados.

Além disso, para a gestão eficaz dos agendamentos, será integrado o [Google Calendar](https://developers.google.com/calendar/api/guides/overview) à aplicação. Essa integração permitirá que os usuários realizem agendamentos, bem como efetuem remarcações, de forma precisa e eficiente. O Google Calendar é amplamente reconhecido por sua confiabilidade e recursos de gerenciamento de tempo, tornando-o uma escolha ideal para essa finalidade.

Essas escolhas tecnológicas refletem nosso compromisso com a excelência e a eficiência na entrega de um aplicativo de agendamento de cortes de cabelo de alta qualidade.

## Requisitos do Aplicativo
- Listagem de Barbeiros:
A aplicação deve exibir uma lista de barbeiros disponíveis para agendamento.

- Visualização de Calendários:
Ao clicar em um barbeiro, o usuário deve ser capaz de visualizar os calendários que exibem os dias disponíveis para agendamento.

- Agendamento de Horários:
Os usuários devem ter a capacidade de agendar horários específicos em um determinado dia para o barbeiro escolhido.

- Login Individual:
A aplicação deve suportar logins individuais, permitindo que diferentes barbearias acessem a plataforma com contas exclusivas.

- Preferências do Cliente:
Os clientes devem ter a opção de inserir informações sobre suas preferências de agendamento, como o tipo de serviço desejado (cortar barba, barba e cabelo, apenas cabelo, etc.).

- Remoção de Barbeiros:
Deve haver uma funcionalidade que permita a remoção de barbeiros da lista disponível para agendamento.

- Cancelamento e Remarcação:
Os usuários devem ter a possibilidade de cancelar ou remarcar horários agendados, observando prazos definidos para tais ações.

## Protótipo do Aplicativo
<a href="https://www.figma.com/file/o4e58W8FlqMddVGotoTA0k/Projeto-Mobile?type=design&node-id=3-4&mode=design&t=wkEiOl3i6jK8onPs-0" target="_blank"><img src="https://img.shields.io/badge/Figma-F24E1E?style=for-the-badge&logo=figma&logoColor=white" alt="Figma"></a>

Apertando o botão estaremos indo para a vizualição das telas no Figma ou se preferir copie e cole esse link no navegador. ⤵
https://www.figma.com/file/o4e58W8FlqMddVGotoTA0k/Projeto-Mobile?type=design&node-id=3-4&mode=design&t=wkEiOl3i6jK8onPs-0

## Documentação Técnica
Abaixo segue o link da documentação técnica do projeto Mobile que será desenvolvido ao longo do período. ⤵
[https://docs.google.com/document/d/1r6L6nHxV7g071uZRLE6I9swU5mlf7cb10IbETOMx7Y4/edit]


## Como funciona a Arquitetura VIPER 🐍
Anos atrás, a Apple adotava o modelo arquitetural MVC como padrão para que seus desenvolvedores pudessem seguir seus projetos, e dava total suporte para que essa decisão fosse adotada. Com o passar dos anos, a partir do momento em que os projetos foram se tornando de larga escala e as equipes cada vez maiores e distribuídas, os problemas referentes a essa arquitetura que citamos anteriormente começaram a aparecer e se tornaram uma grande dor de cabeça para todas as pessoas.

Dessa forma, buscando uma alternativa, uma nova arquitetura foi proposta, baseada inteiramente nos conceitos do clean architecture. Assim surgiu o VIPER (View Interactor Presenter Entity Router), que tem a seguinte estruturação:

<img src="https://www.redspark.io/wp-content/uploads/2020/03/Screen-Shot-2020-02-03-at-10.48.10-1024x345.png" alt="Figma">

View: responsável por receber as entradas do usuário e redirecionar a quem sabe de fato lidar com ela, o seu Presenter. A View conceitualmente conhece seu único Presenter.

Presenter: o Presenter não sabe lidar com todo tipo de requisições. Algumas ele de fato vai dar conta de processar por si só, mas outras ele apenas sabe a quem enviar a depender do comando recebido. Essa camada tem conhecimento de quem é sua View, pois ele precisa atualizá-la. Essa camada também conhece a camada de Router e Interactor.

Router: é responsável por manter as funções de trocas de telas e troca de dados entre elas.

Interactor: é a camada responsável por fazer chamadas a fontes de dados, como banco de dados ou API externas. Essa camada conhece a Entity e faz uso da mesma para montar a resposta das requisições.

Entity: camada que contém a estrutura dos dados a ser utilizado na aplicação.

É interessante observar que aqui existe uma liberdade para escolher a forma de isolamento entre as camadas, que pode ser feita sem maiores dificuldades através de interfaces ou o padrão observer.

<h3>Um exemplo prático</h3>

Mostrando como de fato funcionaria a aplicação de uma arquitetura com estes conceitos explicados na plataforma Android, abaixo temos uma sequência de códigos de cada camada, ilustrando o que foi mostrado acima sobre cada uma delas.

A aplicação em si é bastante simples e com a finalidade apenas de aprendizado. Em curtas palavras, ele possui duas telas: na primeira é possível clicar em um botão para gerar uma frase aleatória e na segunda a frase é exibida, junto com um novo botão para gerar um novo texto.

[LINK PARA IMAGEM DO PROJETO]
https://miro.medium.com/v2/resize:fit:720/format:webp/1*_-zSCAtoEjikrXuzV1qjzA.png 

Primeiro podemos começar pelo código da nossa View, que como comentei basicamente vai receber alguma ação do usuário e repassar para que a mesma seja processada mais adiante no Presenter.

```kotlin
package com.diogocabral.viperSampleApp.view

import android.os.Bundle
import android.support.v7.app.AppCompatActivity
import com.diogocabral.viperSampleApp.R
import com.diogocabral.viperSampleApp.presenter.MainPresenter
import com.diogocabral.viperSampleApp.view.utils.mainActivityComponent

import kotlinx.android.synthetic.main.main_activity.btn_main_new_phrase
import javax.inject.Inject

class MainActivity : AppCompatActivity() {

    @Inject
    lateinit var presenter: MainPresenter

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.main_activity)

        mainActivityComponent.inject(this)

        btn_main_new_phrase.setOnClickListener {
            presenter.onSeePhraseClicked()
        }
    }

    override fun onDestroy() {
        super.onDestroy()
        presenter.disposeCalls()
    }
}
```

Uma vez passada adiante, a requisição vai para o Presenter, que por sua vez precisa lidar com duas coisas: uma chamada a uma API externa e uma troca de tela com passagem de dados quando a primeira ação for completada. Para isso, com o seu conhecimento das camadas, ele faz uso do Interactor para a primeira ação (utilizando o padrão Observer) e do Router para a segunda, como mostra o código abaixo.

```kotlin
package com.diogocabral.viperSampleApp.presenter

import android.util.Log
import com.diogocabral.viperSampleApp.interactor.PhraseInteractor
import com.diogocabral.viperSampleApp.router.goToPhrasesScreen
import com.diogocabral.viperSampleApp.view.MainActivity
import io.reactivex.disposables.Disposable
import javax.inject.Inject

class MainPresenter @Inject constructor(
        private val view: MainActivity,
        private val interactor: PhraseInteractor) {

    var disposable: Disposable? = null

    fun onSeePhraseClicked() {
        disposable = interactor.fetchPhrases().subscribe({ randomPhrase ->
            randomPhrase?.let {
                goToPhrasesScreen(view, randomPhrase)
            }
        }, { e ->
            Log.e("MainPresenter", e.message, e)
        })
    }

    fun disposeCalls() {
        if (disposable != null && disposable?.isDisposed == false) {
            disposable?.dispose()
        }
    }
}
```

Neste exemplo, o Router é apenas um arquivo Kotlin com as funções de transição e passagem de dados, como deve ser em sua essência.

```kotlin
package com.diogocabral.viperSampleApp.router

import android.app.Activity
import android.content.Intent
import com.diogocabral.viperSampleApp.view.PhrasesActivity

private const val PHRASE_INTENT_EXTRA = "initialPhrase"

fun goToPhrasesScreen(view: Activity, initialPhrase: String) {
    val intent = Intent(view, PhrasesActivity::class.java)
    intent.putExtra(PHRASE_INTENT_EXTRA, initialPhrase)
    view.startActivity(intent)
}
```

O Interactor neste exemplo apenas lida com a consulta de uma frase aleatória para uma API externa retornando um Observable. Por utilizarmos ReactiveX e Retrofit2 nesse exemplo e para fazermos uma separação mais clara de responsabilidades, existe um arquivo de serviço, que vai lidar puramente com o endpoint da API que estamos consultando e que vai fazer o relacionamento da resposta com a estrutura que montamos na camada de entidades. As classes Interactor e Service podem ser vistos nos exemplos abaixo.

```kotlin
package com.diogocabral.viperSampleApp.interactor

import com.diogocabral.viperSampleApp.entity.utils.getRandomElement
import com.diogocabral.viperSampleApp.interactor.service.PhrasesService
import io.reactivex.Observable
import io.reactivex.android.schedulers.AndroidSchedulers
import io.reactivex.schedulers.Schedulers
import javax.inject.Inject


class PhraseInteractor @Inject constructor(
        private val phrasesService: PhrasesService){
    fun fetchPhrases(): Observable<String?> {
        return phrasesService.fetchRandomPhrase(10)
                .map { it.phrases.getRandomElement()?.joke }
                .subscribeOn(Schedulers.io())
                .observeOn(AndroidSchedulers.mainThread())
    }
}
```

```kotlin
package com.diogocabral.viperSampleApp.interactor.service

import com.diogocabral.viperSampleApp.entity.PhraseResultEntity
import io.reactivex.Observable
import retrofit2.http.GET
import retrofit2.http.Path

interface PhrasesService {

    @GET("random/{quantity}")
    fun fetchRandomPhrase(@Path("quantity") quantity : Int) : Observable<PhraseResultEntity>
}
```

Por fim, temos os arquivos da camada Entity, que nada mais são do que um mapa da resposta do serviço na nossa aplicação, para podermos usar os dados retornados como objetos manipuláveis.

```kotlin
package com.diogocabral.viperSampleApp.entity

import com.google.gson.annotations.SerializedName

data class PhraseResultEntity(@SerializedName("type") var type: String,
                         @SerializedName("value") var phrases: List<PhraseEntity>)
```

<h3>Conclusão</h3>
o VIPER vem como mais uma alternativa, que traz as vantagens de deixar uma composição de estrutura de projeto clara, limpa e direta. Ela também auxilia na aplicação do TDD como ferramenta de guia de desenvolvimento de código, o que é bastante interessante para manter a qualidade e a documentação do seu projeto como um todo.






