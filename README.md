//
//  ViewController.swift
//  tipcalculator
//
//  Created by David Bui on 12/29/18.
//  Copyright © 2018 David Bui. All rights reserved.
//

import UIKit

class ViewController: UIViewController {
    @IBOutlet weak var tipLabel: UILabel!
    @IBOutlet weak var tipControll: UISegmentedControl!
    
    @IBOutlet weak var billField: UITextField!
    @IBOutlet weak var totalLabel: UILabel!
    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view, typically from a nib.
    }

    @IBAction func onTap(_ sender: Any) {
        view.endEditing(true)
    }
    
    @IBAction func calculatetip(_ sender: Any) {
        let tipPercentages = [0.15,0.2,0.25]
        let bill = Double(billField.text!) ?? 0
        let tip = bill * tipPercentages[tipControll.selectedSegmentIndex]
        let total = bill + tip
        tipLabel.text = String(format: "$%.2f", tip)
        totalLabel.text = String(format: "$%.2f", total)
    }
}

