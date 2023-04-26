# 合在一起1
以下是按照格式整理好的代码，已去掉行号：

```java
public class ReportGenerator {
    protected String title;
    public boolean writeHTML;

    public ReportGenerator(boolean shouldWriteHTML) {
        writeHTML = shouldWriteHTML;
    }

    public void setTitle(String title) {
        this.title = title;
    }

    public boolean isSimilar(ExamScript s1, ExamScript s2) {
        // Implementation hidden
    }

    // Must be called before printContent
    public void printTitle() {
        String report = "";
        if (writeHTML) {
            report += String.format("<h1>%s</h1>\n", title);
        } else {
            report += String.format("%s\n", title);
        }
        System.out.println(report);
    }

    // printTitle should always be called before printContent
    public void printContent(Exam e) {
        String report = "";
        if (writeHTML) {
            report += String.format("<h1>Exam Report for exam %s</h1>\n", e.name);
            for (ExamScript s : e.submissions) {
                boolean isSimilarToAny = false;
                for (ExamScript s2 : e.submissions) {
                    isSimilarToAny = isSimilar(s, s2) || isSimilarToAny;
                }
                report += String.format("<li>%s | %s | %s</li>\n", s.student, s.timeTaken.toString(), isSimilarToAny);
                // More reporting, unshown
            }
        } else {
            report += String.format("Exam Report for exam %s\n", e.name);
            for (ExamScript s : e.submissions) {
                boolean isSimilarToAny = false;
                for (ExamScript s2 : e.submissions) {
                    isSimilarToAny = isSimilar(s, s2) || isSimilarToAny;
                }
                report += String.format("%s, %s, %s\n", s.student, s.timeTaken.toString(), isSimilarToAny);
                // More reporting, unshown
            }
        }
        System.out.println(report);
    }
}

public class Exam {
    public String name;
    public ArrayList<ExamScript> submissions;

    // Date of exam
    public int day;
    public int month;
    public int year;

    public Exam(String name) {
        this.name = name;
        submissions = new ArrayList();
    }

    public Exam(String name, int day, int month, int year) {
        this.name = name;
        this.day = day;
        this.month = month;
        this.year = year;
    }

    public ArrayList<ExamScript> getSubmissions() {
        return submissions;
    }
}


public class ExamScript {
    public Student student;
    public String answer;
    public Time timeTaken;

    public ExamScript(Student student, String answer, Time timeTaken) {
        this.student = student;
        this.answer = answer;
        this.timeTaken = timeTaken;
    }
}

public class Student {
    private int guid;
    public boolean hasExtraTime;

    public Student(int guid) {
        this.guid = guid;
    }

    public void setExtraTime() {
        hasExtraTime = true;
    }
}
```



---


# 代码 宣萱

```java
public class ReportGenerator {
	protected String title;
	public boolean writeHTML;

	public ReportGenerator(boolean shouldWriteHTML) {
		writeHTML = shouldWriteHTML;
	}

	public void setTitle(String title) {
		this.title = title;
	}

	public boolean isSimilar(ExamScript s1, ExamScript s2) {
	// Implementation hidden
	}

	// Must be called before printContent
	public void printTitle() {
		String report = "";
		if (writeHTML) {
			report += String.format("<h1>%s</h1>\n", title);
		} else {
			report += String.format("%s\n", title);
		}
	System.out.println(report);
	}

	// printTitle should always be called before printContent
	public void printContent(Exam e) {
		String report = "";
		if (writeHTML) {
			report += String.format("<h1>Exam Report for exam %s</h1>\n",
						e.name);
			for (ExamScript s : e.submissions) {
				boolean isSimilarToAny = false;
				for (ExamScript s2 : e.submissions) {
 					isSimilarToAny = isSimilar(s, s2) || isSimilarToAny;
 				}
 				report += String.format("<li>%s | %s | %s</li>\n",
							s.student, s.timeTaken.toString(),
							isSimilarToAny);
				// More reporting, unshown
			}
		} else {
			report += String.format("Exam Report for exam %s\n", e.name);
			for (ExamScript s : e.submissions) {
				boolean isSimilarToAny = false;
				for (ExamScript s2 : e.submissions) {
					isSimilarToAny = isSimilar(s, s2) || isSimilarToAny;
				}
				report += String.format("%s, %s, %s\n",
							s.student, s.timeTaken.toString(),
							isSimilarToAny);
				// More reporting, unshown
			}
		}
		System.out.println(report);
	}
}
```

```java
public class Exam {
	public String name;
	public ArrayList<ExamScript> submissions;

	// Date of exam
	public int day;
	public int month;
	public int year;

	public Exam(String name) {
		this.name = name;
		submissions = new ArrayList();
	}

	public Exam(String name, int day, int month, int year) {
		this.name = name;
		this.day = day;
		this.month = month;
		this.year = year;
	}

	public ArrayList<ExamScript> getSubmissions() {
		return submissions;
	}
}
```

```java
public class ExamScript {
	public Student student;
	public String answer;
	public Time timeTaken;

	public ExamScript(Student student, String answer, Time timeTaken) {
		this.student = student;
		this.answer = answer;
		this.timeTaken = timeTaken;
	}
}
```

```java
public class Student {
	private int guid;
	public boolean hasExtraTime;

	public Student(int guid) { this.guid = guid; }
	public void setExtraTime() { hasExtraTime = true; }
}
```

```java
public class Student {
	private int guid;
	public boolean hasExtraTime;

	public Student(int guid) { this.guid = guid; }
	public void setExtraTime() { hasExtraTime = true; }
}
```

![](assets/Pasted%20image%2020230426124913.png)


# 2019
~~~java
import uk.ac.glasgow.network.*; // classes for e.g. NetworkStream, NetworkGlobals

public class NetworkEventAnalyser{
  public byte[] maskPattern;
  public NetworkEventAnalyser(){
    //...
  }

  public boolean analyze(byte[] data, String timestamp, NetworkConfig config)
  {
    boolean patternFound = false;
    if(NetworkGlobals.DO_VIRUS_CHECK && findPattern(maskPattern,data)) {
      LogUtils.fileExistsElseCreate(NetworkGlobals.FILE_NAME);
      LogUtils.writeToExistingFile(NetworkGlobals.FILE_NAME,"Issue");

      config.trustedCommunication = -1;
      patternFound = true;
    }
    return patternFound;
  }

  public void cleanHarddrive(String disk) {
  /// ...
  }
}

public class LogUtils{

  public static void fileExistsElseCreate(String fnName) {
  /// ... check if file exists; else create the file
  }

  public static void writeToExistingFile(String fnName, String msg) {
  /// ... append msg to the existing file
  }
}

public class NetworkVirusScanner{
  public NetworkConfig networkConfig;
  private NetworkEventAnalyser eventAnalyzer;

  public NetworkVirusScanner(NetworkConfig config) {
    networkConfig = config;
    networkConfig.trustedCommunication = +1;

    eventAnalyzer = new NetworkEventAnalyser();
    eventAnalyzer.maskPattern = "sudo rm ./ -f -r".getBytes();

    ///...

    LogUtils.fileExistsElseCreate(NetworkGlobals.FILE_NAME);
    LogUtils.writeToExistingFile(NetworkGlobals.FILE_NAME,"Running…”);

  }

  public void networkEventHandler(NetworkEvent event){
  eventAnalyzer.analyze(event.dataPacket, event.timeStamp, networkConfig);
   
    ///...
  }
}
~~~

1.  Stamping Coupling
![](assets/Pasted%20image%2020230426174454.png)
![](assets/Pasted%20image%2020230426175838.png)
timestamp这个参数没有使用
特征: 组件之间传递的信息比需要的信息要多. 函数传递的参数太多,超过所需要的参数.

2.  Content Coupling
![](assets/Pasted%20image%2020230426174739.png)
是指一个模块在某种方式下直接访问了另一个模块的内部数据或操作.

3. Common Data Coupling
![](assets/Pasted%20image%2020230426181825.png)

4. Control Coupling
![](assets/Pasted%20image%2020230426182307.png)

但是这个也算是公共数据耦合.

5. 


内容耦合（content coupling）：
特点：发生在模块之间共享数据或信息时，即被调用模块依赖于调用模块中特定的数据或信息；或者一个模块或者类访问了另一个模块或者类中的内部内容
第16行中，-1直接被赋值给了config中的trustedCommunication参数；（这种是不是？？）
第47行中，eventAnalyzer.maskPattern被直接设置为一个byte数组，即NetworkVirusScanner模块直接修改了NetworkEventAnalyser模块中的数据；
控制耦合（Control Coupling）：
特点：一个类调用了另一个类的变量并控制了流程或者行为
第9行，eventAnalyzer.analyze()方法的第三个参数config就是一个控制参数，并在第16行直接控制了其变量值，并影响了NetworkVirusScanner 中的操作（在构造函数中给该属性赋值）。这种控制耦合导致两个模块之间高度耦合，并且使得在修改其中一个模块时需要考虑对另一个模块的影响。
第51和52行，NetworkVirusScanner 类中的构造函数中调用了 LogUtils 类的 fileExistsElseCreate 和 writeToExistingFile 方法，控制了日志记录的行为。这种控制耦合使得 NetworkVirusScanner 类依赖于 LogUtils 类的实现，难以在不修改 LogUtils 类的情况下对 NetworkVirusScanner 进行独立测试和维护。
标记耦合（Stamp Coupling）：
特点：组件之间传递的信息特性比需要的要多
第9行，传入的String参数在函数中没有用到timestamp，
常见数据耦合（Common Data Coupling）：
特点：全局变量。
第12行，有一个全局变量NetworkGlobals.DO_VIRUS_CHECK
时间耦合（Temporal Coupling）：
第51和52行，在NetworkVirusScanner类中，eventAnalyzer实例的创建和LogUtils类的方法调用是在构造函数中完成的，存在时间耦合。
特点：时间耦合是指一个模块的行为依赖于另一个模块的执行顺序或时间，从而产生的耦合关系。