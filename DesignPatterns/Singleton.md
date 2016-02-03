## 💍 Singleton
------------

The singleton pattern ensures that only one object of a particular class is ever created.
Do not overuse this pattern!

### Example .h:

````objective-c

@interface AppBliss: NSObject 

+ (instancetype)sharedManager;
	
@end

````


### Example .m:

````objective-c

#import "AppBliss.h"

@implementation

+ (id)sharedManager {
    static AppBliss *sharedMyManager = nil;
    static dispatch_once_t onceToken;
    dispatch_once(&onceToken, ^{
        sharedMyManager = [[self alloc] init];
    });
    return sharedMyManager;
}

@end

````

### Usage:

````objective-c

AppBliss *manager = [AppBliss sharedManager];

````

### Tips: 

You should be able to prefix your singleton class name with "App" and it would still make sense. ie: AppDataAccess, AppMusicPlayer, etc


# TO DO:
- [ ] Explain why singletons should be avoided
