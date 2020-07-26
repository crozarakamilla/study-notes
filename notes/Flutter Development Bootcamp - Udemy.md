---
tags: [flutter]
title: Flutter Development Bootcamp - Udemy
created: '2020-07-26T00:48:34.017Z'
modified: '2020-07-26T00:53:15.904Z'
---

# Flutter Development Bootcamp - Udemy

- Documentação: https://api.flutter.dev/flutter/material/Scaffold-class.html
- Course resources: https://github.com/londonappbrewery/Flutter-Course-Resources
- Configurações gerais da aplicação: pubspec.yaml
- Gerar ícones para aplicativos: https://appicon.co/ -> gera pastas com ícones para Android e Iphone. 
	- Colar ícones para android na pasta android/app/src/main/res 
	- Colocar ícones para IOs dentro de ios/Runner/Assets.xcassets
- Configurar os ícones para estilo redondo: android/app/src/main -> Right Click on 'res' folder -> New Image Assets e escolher as imagens a serem tratadas
- Imagens e ícones para aplicativos:
	- https://icons8.com/
	- https://www.vecteezy.com/
- HOT RELOAD: para funcionar é necessário ter todas as modificações dentro de FlutterStateless ou Statefull widget

```
//aplicação sem hot reload

import 'package:flutter/material.dart';

void main() {
  runApp(
    MaterialApp(
      home: Scaffold(
        backgroundColor: Colors.teal,
        body: Container(),
      ),
    ),
  );
}
```

```
//aplicação com hot reload

import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        backgroundColor: Colors.teal,
        body: Container(),
      ),
    );
  }
}
```

- SAFE AREA: mantém o conteúdo em uma área segura na tela do dispositivo

```
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        backgroundColor: Colors.teal,
        body: SafeArea(
          child: Container(
            child: Text('Hello'),
            color: Colors.white,
          ),
        ),
      ),
    );
  }
}
```

- mainAxisSize: limita o tamanho da coluna para caber apenas os elementos contidos nela

- Flutter Cookbook: https://flutter.dev/docs/cookbook

- Flutter Themes: temas são compartilhados por todas as páginas do app..

```
//copyWith() sobrescreve apenas as propriedades desejadas a partir de um dado tema

theme: ThemeData.dark().copyWith(
        primaryColor: Color(0xFF0A0E21),
        scaffoldBackgroundColor: Color(0xFF0A0E21),
      ),

//o tema de qualquer Widget pode ser mudado apenas wrapping com Theme() widget

floatingActionButton: Theme(
        data: ThemeData.light(),
        child: FloatingActionButton(
          child: Icon(Icons.add),
        ),
      ),
```

```
//ao usar Containers com BoxDecoration a propriedade color tem que estar dentro de BoxDecoration
Container(
        margin: EdgeInsets.all(15.0),
        height: 200.0,
        width: 170.0,
        decoration: BoxDecoration(
            color: Color(0xFF1D1E33),
            borderRadius: BorderRadius.circular(10.0)),
      ),
```

```
//detectar gestos em widgets
child: GestureDetector(
                    onTap: () {
                      print('MALE card was pressed');
                      setState(() {
                        updateColor(1);
                      });
                    },
```

```
// OF Returns the data from the closest [SliderTheme] instance that encloses the given context. 
// Defaults to the ambient [ThemeData.sliderTheme] if there is no [SliderTheme] in the given build context

SliderTheme(
                    data: SliderTheme.of(context),
                    child: Slider(
                      value: height.toDouble(),
                      min: 80.0,
                      max: 220.0,
                      activeColor: Color(0xFFEB1555),
                      inactiveColor: Color(0xFF8D8E98),
                      onChanged: (double newValue) {
                        setState(() {
                          height = newValue.round();
                        });

                      },
                    ),
                  ),
```
