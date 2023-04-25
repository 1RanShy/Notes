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