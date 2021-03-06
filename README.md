RPSlidingMenu
=============

A collection view menu in the style of UltraVisual.


![alt text](http://dl.dropboxusercontent.com/u/19170848/RPSlidingMenu_1.png "RPSlidingMenu Example")
[![RPSlidingMenuVideo](http://img.youtube.com/vi/jUsxavJp4l8/0.jpg)](http://www.youtube.com/watch?v=jUsxavJp4l8)

## Installation

### From CocoaPods

Add `pod 'RPSlidingMenu'` to your Podfile

## Usage

(see sample Xcode project in `/Demo`)

Create a new file that inherits from RPSlidingMenuViewController

Override the following methods:
```
// return the number of menu items
-(NSInteger)numberOfItemsInSlidingMenu;
// set properties of the cell like the textLabel.text, detailLabel.text and backgroundImageView.image
- (void)customizeCell:(RPSlidingMenuCell *)slidingMenuCell forRow:(NSInteger)row;
// optionally to handle a menu item being tapped
- (void)slidingMenu:(RPSlidingMenuViewController *)slidingMenu didSelectItemAtRow:(NSInteger)row;
```

##Example of code in .m
```
-(NSInteger)numberOfItemsInSlidingMenu{
    return 10; // 10 menu items
}

- (void)customizeCell:(RPSlidingMenuCell *)slidingMenuCell forRow:(NSInteger)row{

    slidingMenuCell.textLabel.text = @"Some Title";
    slidingMenuCell.detailTextLabel.text = @"Some longer description that is like a subtitle!";
    slidingMenuCell.backgroundImageView.image = [UIImage imageNamed:@"some_image"];

}

- (void)slidingMenu:(RPSlidingMenuViewController *)slidingMenu didSelectItemAtRow:(NSInteger)row{
    // when a row is tapped do some action like go to another view controller
    UIAlertView *alert = [[UIAlertView alloc] initWithTitle:@"Row Tapped"
                                                    message:[NSString stringWithFormat:@"Row %d tapped.", row]
                                                   delegate:nil
                                          cancelButtonTitle:@"OK"
                                          otherButtonTitles: nil];
    [alert show];
}
```

##Notes

- In the demo I used images that were 320x210.  They just need to be big enough to cover the cells size

## Contact

Follow Robots & Pencils on Twitter ([@robotsNpencils](https://twitter.com/robotsNpencils))

### Maintainers

- [Paul Thorsteinson](http://github.com/paulthorsteinson) ([@codezy](https://twitter.com/codezy))


## License

RPSlidingMenu is available under the MIT license. See the LICENSE file for more info.
