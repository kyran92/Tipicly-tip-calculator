//
//  ViewController.swift
//  tipicly
//
//  Created by Kyran Richardson on 12/11/15.
//  Copyright © 2015 Kyran Richardson. All rights reserved.
//

import UIKit

class ViewController: UIViewController {

    @IBOutlet weak var settingsButton: UIButton!
    @IBOutlet weak var billField: UITextField!
    @IBOutlet weak var tipLabel: UILabel!
    @IBOutlet weak var totalLabel: UILabel!
    @IBOutlet weak var tipControl: UISegmentedControl!
    let defaults = NSUserDefaults.standardUserDefaults()
    
    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view, typically from a nib.

    tipLabel.text = "$0.00"
    totalLabel.text = "$0.00"
        let image = UIImage(named: "logo")
        self.navigationItem.titleView = UIImageView(image:image)
        
        let bar:UINavigationBar! =  self.navigationController?.navigationBar
        
        bar.setBackgroundImage(UIImage(), forBarMetrics: UIBarMetrics.Default)
        bar.shadowImage = UIImage()
        bar.backgroundColor = UIColor(red: 0.0, green: 0.8, blue: 0.8, alpha: 0.0)
        
        
        self.view.backgroundColor = UIColor(patternImage: UIImage(named: "BG2.jpg")!)
    
        
    }

    override func didReceiveMemoryWarning() {
        super.didReceiveMemoryWarning()
        // Dispose of any resources that can be recreated.
    }
    
    @IBAction func onEditingChanged(sender: AnyObject) {
        updateTip()
    }
    func updateTip() {
        let tipPercentages = [0.18, 0.2, 0.22]
        let tipPercentage = tipPercentages [tipControl.selectedSegmentIndex]
        
        let billAmount = NSString(string:billField.text!).doubleValue
        let tip = billAmount * tipPercentage
        let total = billAmount + tip
        
        
        tipLabel.text = String(format: "$%.2f", tip)
        totalLabel.text = String(format: "$%.2f", total)
        
        fadeInTotal()
    }
    

    @IBAction func onTap(sender: AnyObject) {
        view.endEditing (true)
        
    }
    
        
    override func viewWillAppear(animated: Bool) {
        super.viewWillAppear(animated)
        
        let defaults = NSUserDefaults.standardUserDefaults()
        let tipDefault = defaults.integerForKey("default_tip")
        print("got default tip: \(tipDefault)")
        switch tipDefault {
        case 0...2:
            tipControl.selectedSegmentIndex = tipDefault
        default:
            tipControl.selectedSegmentIndex = 0
        }
        
        // Recalculate the tip
        updateTip()
    }
    func fadeInTotal() {
        self.totalLabel.alpha = 0
        UIView.animateWithDuration(0.4, delay: 0.0, options: UIViewAnimationOptions.CurveEaseIn,
            animations: {
                self.totalLabel.alpha = 1 }, completion: nil )
}
}
