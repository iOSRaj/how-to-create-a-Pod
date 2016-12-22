# How to Create Pod

Most of the iOS developers know what is Pod, how it reduces the complexity of the development with more re-usable and more elegant way to scale projects .

Its basically a dependency manager for iOS where the required componets can be added as a lego to the projects

### Basic Commands of Pod 

```sh
$ sudo gem install cocoapods
$ pod setup --verbose
$ pod spec create [NAME]
$ pod init
$ pod install --verbose
$ pod lib lint
```

Lets get into the nitty-gritty of the cocopoads development with very simple steps.

### Step 1
* Create a simple Xcode project 
* Go to the root of the folder, where the Xcode project has created
### Step 2
* Use the command  ```$ pod spec create PODNAME```
* Once done, We can see a file name **[PODNAME].podsepc** in the directory
* Just open and We will See a list of descriptions about various keywords which starts with Pod.....

```sh
Pod::Spec.new do |s|
```
### Step 3
* So curious what it is in the Pod spec, Its the heart of the POD which describes the pod name, path of the source files, assets , target OS, frameworks, to be included etc.., 
* Give the name for POD which be called heerafter, in the name keyword. Like this, we have set of keywords needs to be addressed
* Example of the Sample Pod Structure is give below
```sh
Pod::Spec.new do |s|
s.name             = 'CodeScannerHelper'
s.version          = '1.0.0'
s.summary          = 'CodeScannerHelper pod to scan all the BarcodeTypes'

s.description      = <<-DESC
CodeScannerHelper pod for use with  swift projects
DESC

s.homepage         = 'https://stash.eden.klm.com/projects/MOBILE/repos/CodeScanner'
s.license          = "Raj"
s.author           = { 'Raj' => 'rajkumargkr@gmail.com' }
s.source           = { :git => 'https://github.com/iOSRaj/CodeScannerHelper.git', :tag => s.version }

s.ios.deployment_target = '8.0'
s.source_files =   'ScannerClass/**/*.{swift}'
s.dependency "AFNetworking", ">= 1.22.0"
s.resources      = ['ScannerClass/*.{storyboard,xib}',
'ScannerClass/*.xcassets']

s.preserve_paths = 'ScannerClass/*'

end
```

Lets go in to the keywords in detail.
* **s.name** -> Name of the pod
* s.version -> Version of the Pod
* s.summary -> A short one liner
* s.description -> In-depth explanation of the Pod, what it does etc..,
* s.homepage  -> More info about the pod in the URL
* s.license  -> Mention the License MIT, BSD, etc..,
* s.source -> Specify the location from where the source should be retrieved (git, SVN etc..,)
* s.ios.deployment_target -> iOS or OS X,  specify the platform and the deployment target
* s.source_files -> Give a folder where codes needs to inculded like swift, h, m
* s.resources  -> A list of resources included with the Pod
* s.preserve_paths -> You can preserve files from being cleaned by giving the folder 
* s.dependency -> If the pod includes third party dependencies like SwiftyJson, Afnetworking 

### Step 4
Lets get into the real business of creating a Pod which is a dynamic framework
* In the Asssitance Navigator, Click on the + at the bottom left corner, where the Template window is presented
* Under the **Template -> Framework & Library section -> Choose CocoaTouch framework**
* Then Next, give the product name finish. No need to select anything from the template

### Step 5

Create a folder in the root of the project, where the files which needs to be exposed are added into this 

* Create a new file where the core functionality needs to be added from the File-> New from Xcode
* Make sure file is added into the Target of the Framework not in the app target
* Define and Declare whatever needs to be added into the class
* Also make sure Class is defined as Public so that it can be accessed from the other class

### Step 6
So Excited to test how it works, Just import podName in the current application 
Then its ready.

### Step 7
To test exactly with the other application locally
* As usual ```$ pod init ```
* Give the pod name in the podfile, then in the podfile just give the path of the folder where you made a pod then the Pod name 
* ```$ pod 'Name', :path => '~/code/Pods/'```

### Step 8
* ```Import Podname ```, Use the methods in it and Then get set ready to go 🏃


