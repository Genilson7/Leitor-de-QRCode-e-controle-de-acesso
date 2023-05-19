# Leitor-de-QRCode-e-controle-de-acesso
Protótipo de um leitor de QRCode e auxiliador no controle de acesso de materiais para empresas;
 Uma breve descrição do funcionamento e uso para quem quiser reproduzir.
O APP é um leitor de QRCode que serve para controle de acesso e estoque podendo ser ainda utilizado para outras demandas. O aplicativo é simples, consiste em abrir o Aplicativo em seu smartphone, entrar no Power apps, se o mesmo ainda não estiver vinculado ao Apple store ou google play, e com apenas 1 clique, abre o leitor e após leitura do QRCode, já abre as informações como, código do material e estoque. Sempre em conexão através do SAHA e ou SQL/Banco de dados da empresa, diretamente para uma planilha Excel ou em outros APPs como SAP.
 O software desenvolvido e a documentação de código.
 ![IMG_7275](https://github.com/Genilson7/Leitor-de-QRCode-e-controle-de-acesso/assets/110739927/58a155c5-c8ae-42a7-9853-a8b949630ca5)
O software que utilizei para desenvolvimento é o Power apps. O power apps assim como o Kodular, são uma ferramenta que utiliza a linguagem No-Code, tendo um conhecimento em lógica ele é de fácil utilização e de uma rápida curva de aprendizagem, arrastando componentes na tela e utilizando blocos para desenvolver. A sua programação é simples, um ponto chave para a fluidez em seu aprendizado, utilizando de eventos e os famosos blocos de encaixe. No projeto em questão utilizei apenas a noção em liguagem de programação.
O código a seguir é o que aparece após a criação do app sendo o código fonte da página:

<div class="appmagic-image no-focus-outline" data-bind="{
      style: {
        paddingTop: properties.PaddingTop,
        paddingRight: properties.PaddingRight,
        paddingBottom: properties.PaddingBottom,
        paddingLeft: properties.PaddingLeft,
        backgroundColor: autoProperties.Fill,
        height: '100%',
        width: '100%',
        opacity: properties.Transparency() >= 1 ? '0' : 1 - properties.Transparency(),
        visibility: properties.Transparency() >= 1 ? 'hidden' : ''
      },
      visible: properties.Visible
    }" style="padding: 0px; background-color: rgba(0, 0, 0, 0); height: 100%; width: 100%; opacity: 1;">
      <!-- ko if: !$data.imageSrc || !properties.ImagePosition().objectFit || Core.Environment.getBrowserId() === Core.Environment.BrowserId.InternetExplorer --><!-- /ko -->
      <!-- ko if: $data.imageSrc && properties.ImagePosition().objectFit && Core.Environment.getBrowserId() !== Core.Environment.BrowserId.InternetExplorer -->
      <img data-bind="{
          css: {
            'appmagic-image-inner': true,
            rotateHorizontal: $data.hasHorizontalRotation &amp;&amp; $data.hasHorizontalRotation()
          },
          style: {
            height: innerHeight,
            width: innerWidth,
            visibility: imageAvailable() ? innerVisibility() : 'hidden',
            objectFit: properties.ImagePosition().objectFit,
            objectPosition: properties.ImagePosition().objectPosition,
            flex: '0 0 auto',
            borderRadius: '0.1px',
            '-webkit-transform': transform,
            transform: transform
          },
          attr: {
            src: $data.imageSrc &amp;&amp; $data.imageSrc(),
            alt: properties.TabIndex() < 0 &amp;&amp; properties.AccessibleLabel() ? properties.AccessibleLabel() : ''
          },
          event: {
            load: onImageLoad,
            error: onImageError
          }
      }" class="appmagic-image-inner" src="https://pafeblobprodcq.blob.core.windows.net/20220921t000000zc2cfce361ea94f5bad4fcc60c4648ff6/fe7a15ee-12a9-494a-a531-ba9da96ba107/web/Assets/Images/6304a4cb-0075-446d-86f9-f09c656d3b21.png?sv=2018-03-28&amp;sr=c&amp;sig=bIyd35Cm8VD6bf1Z%2Bv%2FFDbuoZGPqJiw%2FwvB%2BjP%2FQYhA%3D&amp;se=2023-05-23T12%3A00%3A00Z&amp;sp=rl" alt="" style="height: 100%; width: 100%; object-fit: contain; object-position: 50% 50%; flex: 0 0 auto; border-radius: 0.1px; transform: matrix(1, 0, 0, 1, 0, 0);">      
      <!-- /ko -->
      <div class="appmagic-image-stub-container">
      </div>
      <button class="appmagic-image-button" data-bind="{
          visible: properties.TabIndex() >= 0,
          text: properties.AccessibleLabel() || '',
          disable: viewState.displayMode() !== AppMagic.Constants.DisplayMode.Edit,
          event: { click: onClickHandler },
          attr: {
            title: properties.Tooltip() || null
          }
      }" tabindex="-1" style="display: none;"></button>
      <div class="appmagic-image-pseudo-button" aria-hidden="true" data-bind="{
          visible: properties.TabIndex() < 0,
          event: { click: onClickHandler },
          attr: {
            title: properties.Tooltip() || null
          }
      }">
      </div>
  </div> 

 A documentação das interfaces, protocolos e módulos de comunicação.

