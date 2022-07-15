# Anchor 
Praticar conceitos para construcao de layouts em IOS

## Moticao
Entneder o uso de Anchor em IOS


## Feature
- Aprendi a construcao de interfaces no IOS
- Aprendi constuir de forma dinamica uma view e maneira fixa
- Centralizar ele no eixo x e y



```swift
//
//  ViewController.swift
//  AnchorsLab
//
//  Created by kenjimaeda on 14/07/22.
//

import UIKit

class ViewController: UIViewController {
	
	override func viewDidLoad() {
		super.viewDidLoad()
		// Do any additional setup after loading the view.
		setupViews()
	}
	
	func setupViews() {
		let labelLeft = makeLabel("upperLeft")
		let labelRight = makeLabel("upperRight")
		let labelLeftButton = makeSecondaryLabel("lowerLeft")
		//evita palavras chaves como button,view
		let buttonBill = makeButton("Play Bill")
		let redView = makeView()
		
		view.addSubview(labelLeft)
		view.addSubview(labelRight)
		view.addSubview(labelLeftButton)
		view.addSubview(buttonBill)
		view.addSubview(redView)
		
		//label a esquerda top
		labelLeft.topAnchor.constraint(equalTo: view.safeAreaLayoutGuide.topAnchor, constant: 8).isActive = true
		labelLeft.leadingAnchor.constraint(equalTo: view.leadingAnchor, constant: 8).isActive = true
		
		//label a direita top
		labelRight.topAnchor.constraint(equalTo: view.safeAreaLayoutGuide.topAnchor, constant: 8).isActive = true
		labelRight.trailingAnchor.constraint(equalTo: view.trailingAnchor, constant: -8).isActive = true
		
		//label a esquerda bottom
		labelLeftButton.bottomAnchor.constraint(equalTo: view.safeAreaLayoutGuide.bottomAnchor, constant: 8).isActive = true
		labelLeftButton.leadingAnchor.constraint(equalTo: view.leadingAnchor, constant: 8).isActive = true
		
		//label a esquerda bottom
		buttonBill.bottomAnchor.constraint(equalTo: view.safeAreaLayoutGuide.bottomAnchor, constant: 8).isActive = true
		buttonBill.trailingAnchor.constraint(equalTo: view.trailingAnchor, constant: -8).isActive = true
		
		//view inicia aqui
	  //centralizar position no centro
		redView.centerXAnchor.constraint(equalTo: view.centerXAnchor).isActive = true
		redView.centerYAnchor.constraint(equalTo: view.centerYAnchor).isActive = true
		
		//altura e largura fixa
//		redView.heightAnchor.constraint(equalToConstant: 100).isActive = true
//		redView.widthAnchor.constraint(equalToConstant: 50).isActive = true
		
		//altura e largura dinamica
		//width
		redView.leadingAnchor.constraint(equalTo: view.leadingAnchor, constant: 20).isActive = true
		redView.trailingAnchor.constraint(equalTo: view.trailingAnchor, constant: -20).isActive = true
		
		//height dinamico
		redView.topAnchor.constraint(equalTo: view.safeAreaLayoutGuide.topAnchor, constant: 100).isActive = true
		redView.bottomAnchor.constraint(equalTo: view.safeAreaLayoutGuide.bottomAnchor, constant: -100).isActive = true
		
		//view finaliza aqui
		
	}
	
	
	func makeLabel(_ text:String) -> UILabel {
		let label = UILabel()
		label.translatesAutoresizingMaskIntoConstraints = false  //importante para funcionar auto layout
		label.backgroundColor = .yellow
		label.text = text
		return label
	}
	
	func makeSecondaryLabel(_ text: String) -> UILabel  {
		let label = UILabel()
		label.translatesAutoresizingMaskIntoConstraints = false
		label.backgroundColor = .yellow
		label.text = text
		label.font = UIFont.systemFont(ofSize: 17)
		label.textColor = .gray
		return label
	}
	
	func makeButton(_ text: String) -> UIButton {
		let button = UIButton()
		button.translatesAutoresizingMaskIntoConstraints = false
		button.backgroundColor = .blue
		button.tintColor = .white
		button.setTitle(text, for: .normal)
		return button
	}
	
	func makeView() -> UIView {
		let view = UIView()
		view.translatesAutoresizingMaskIntoConstraints = false
		view.backgroundColor = .red
		return view
	}
	
	
}





```
