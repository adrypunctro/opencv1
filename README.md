# opencv1

http://opencv-java-tutorials.readthedocs.io/en/latest/01-installing-opencv-for-java.html

```java
private static void loadLibraries()
    {
        try
        {
            InputStream in = null;
            File fileOut = null;
            String osName = System.getProperty("os.name");
            String opencvpath = System.getProperty("user.dir");
            if(osName.startsWith("Windows")) {
                int bitness = Integer.parseInt(System.getProperty("sun.arch.data.model"));
                if(bitness == 32) {
                    opencvpath=opencvpath+"\\opencv\\build\\java\\x86\\";
                }
                else if (bitness == 64) { 
                    opencvpath=opencvpath+"\\opencv\\build\\java\\x64\\";
                } else { 
                    opencvpath=opencvpath+"\\opencv\\build\\java\\x86\\"; 
                }           
            } 
            else if(osName.equals("Mac OS X")){
                opencvpath = opencvpath+"Your path to .dylib";
            }
            System.out.println(opencvpath);
            System.load(opencvpath + Core.NATIVE_LIBRARY_NAME + ".dll");
        } catch (Exception e) {
            throw new RuntimeException("Failed to load opencv native library", e);
        }
    }
```

https://github.com/lessthanoptimal/BoofCV/blob/v0.27/examples/src/boofcv/examples/features/ExampleLineDetection.java
http://boofcv.org/index.php?title=Main_Page
