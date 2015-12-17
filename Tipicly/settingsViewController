//
//  SettingsViewController.swift
//  tipicly
//
//  Created by Kyran Richardson on 12/12/15.
//  Copyright © 2015 Kyran Richardson. All rights reserved.
//

import UIKit

class SettingsViewController: UIViewController {
    @IBOutlet weak var defaultTipControl: UISegmentedControl!

    
    @IBOutlet weak var tipDefault: UISegmentedControl!

      
    
    override func viewDidLoad() {
        super.viewDidLoad()
         self.view.backgroundColor = UIColor(patternImage: UIImage(named: "BG2.jpg")!)
    }
    

    override func didReceiveMemoryWarning() {
        super.didReceiveMemoryWarning()
        
    }
    @IBAction func onEditDefaultTip(sender: UISegmentedControl) {
        let defaults = NSUserDefaults.standardUserDefaults()
        
        defaults.setInteger(sender.selectedSegmentIndex, forKey: "default_tip")
        defaults.synchronize()
        
    }

    override func viewWillAppear(animated: Bool) {
        super.viewWillAppear(animated)
        
        let defaults = NSUserDefaults.standardUserDefaults()
        let tipDefault = defaults.integerForKey("default_tip")
        print("got default tip: \(tipDefault)")
        switch tipDefault {
        case 0...2:
            defaultTipControl.selectedSegmentIndex = tipDefault
        default:
            defaultTipControl.selectedSegmentIndex = 0
            defaults.synchronize()
        }
    }
    /*
    // MARK: - Navigation

    // In a storyboard-based application, you will often want to do a little preparation before navigation
    override func prepareForSegue(segue: UIStoryboardSegue, sender: AnyObject?) {
        // Get the new view controller using segue.destinationViewController.
        // Pass the selected object to the new view controller.
    }
    */

}
