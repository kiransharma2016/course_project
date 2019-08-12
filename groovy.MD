#### groovy example code 
// using explicit argument
def sout = new StringBuilder(), serr = new StringBuilder()

def image_Change=" "
for (item in lst) {
    println "Item: ${item}"
    if ("${item}" == "ubuntu:123" )
        {
        image_Change=true
        println ("found the image")
        break
        }

    //if (item.size() == 0) break
    image_Change=false
}

println "Finishes:${image_Change}"

println "test the version  Tag Passed to function:${versionTag}"
return image_Change
}

def result = test(123)

if ("${result}" == true )
  {
   println ("Result: ${result}")
  }
else
 {
   println "Result: ${result}"
   println "Exiting"
   System.exit(1)
 }

println "Continuing"

