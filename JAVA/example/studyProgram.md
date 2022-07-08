
<StudyInfo.java>

```java

package studyProgram;

public interface StudyInfo {
	
	public void joinStudy(StudyVO[] std);
	public void inputStudy(StudyVO[] std);
	public void updateStudy(StudyVO[] std);
	public void deleteStudy(StudyVO[] std);
	public void outputFine(StudyVO[] std);
	public void outputStudy(StudyVO[] std);
	
}


```

<br>

<StudyInfolm.java>

```java

package studyProgram;

import java.util.Scanner;

public class StudyInfoIm implements StudyInfo {

	Scanner scan = new Scanner(System.in);
	
	static int cnt = 0;
	static String deleteMem = "del";
	
	
	@Override
	public void joinStudy(StudyVO[] std) {
	
		System.out.println(">>가입<<");
		System.out.println("회원번호 : ");
		String memberCode = scan.nextLine();

		if (cnt > 0) {
			for (int i = 0; i < cnt; i++) {
				
				if(std[i].getMemberCode().equals(memberCode)) {
					System.out.println("중복회원!!");
					return;
				}
				
			}
			
			
		}
		
		std[cnt].setMemberCode(memberCode);
		
		System.out.print("회원이름 : ");
		String memberName = scan.nextLine();
		
		std[cnt].setMemberName(memberName);
		
		
		System.out.print("보증금 : ");
		int deposit = scan.nextInt();
		std[cnt].setDeposit(deposit);
		scan.nextLine();
		
		System.out.print("가입날짜 : ");
		String joinDate = scan.nextLine();
		std[cnt].setJoinDate(joinDate);
		
		cnt++;
		System.out.println(">>>가입완료");
		System.out.println();
		
	}

	@Override
	public void inputStudy(StudyVO[] std) {
		
		System.out.println(">>정보입력<<");
		System.out.println("회원번호 : ");
		String memberCode = scan.nextLine();
		
		
		if(cnt > 0) {
			for (int i = 0; i <= cnt; i++) {
				
				if (std[i].getMemberCode().equals(memberCode)) {
					
					System.out.print("스터디날짜 : ");
					String studyDate = scan.nextLine();
					std[i].setStudyDate(studyDate);
					
					System.out.print("챕터정리 : ");
					String chapter = scan.nextLine();
					std[i].setChapter(chapter);
					
					System.out.print("중간점검 : ");
					String chk1 = scan.nextLine();
					std[i].setChk1(chk1);
					
					System.out.print("최종점검 : ");
					String chk2 = scan.nextLine();
					std[i].setChk2(chk2);
					System.out.println();
					return;
					
				}
				
				
			}
			
			
		}else {
			System.out.println();
			System.out.println("가입을 먼저 해주세요.");
		
		}
		
	}

	@Override
	public void updateStudy(StudyVO[] std) {
		System.out.println(">>정보수정<<");
		System.out.print("회원번호 : ");
		String memberCode = scan.nextLine();
		
		if(cnt > 0) {
			for (int i = 0; i <= cnt; i++) {
			
				if(std[i].getMemberCode().equals(memberCode)) {
					
					System.out.println("회원번호 : " + std[i].getMemberCode());
					
					System.out.print("스터디날짜 : ");
					String studyDate = scan.nextLine();
					std[i].setStudyDate(studyDate);
					
					System.out.print("챕터정리 : ");
					String chapter = scan.nextLine();
					std[i].setChapter(chapter);
					
					
					System.out.print("과제 : ");
					String task = scan.nextLine();
					std[i].setTask(task);
					
					System.out.print("중간점검 : ");
					String chk1 = scan.nextLine();
					std[i].setChk1(chk1);
					
					System.out.print("최종점검 : ");
					String chk2 = scan.nextLine();
					std[i].setChk2(chk2);
					System.out.println();
					return;
				}
				
			}
			
		} else {
			System.out.println();
			System.out.println("가입을 먼저해주세요 \n");
		
		}
		
		
	}
	
	public void fineChk(StudyVO[] std) {
		
		String x = "x";
		int fine= 2500;
		int totFine = 0;
		
		if(cnt > 0) {
			for (int i = 0; i < cnt; i++) {
				if(x.equals(std[i].getChapter())) {
					totFine += fine;
					
				}
				
				if(x.equals(std[i].getTask())) {
					 totFine += fine;
				}
				
				if(x.equals(std[i].getChk1())) {
					totFine += fine;
				
				}
				
				if(x.equals(std[i].getChk2())) {
					totFine += fine;
				}
				
				std[i].setFine(totFine);
				std[i].setBalance(std[i].getDeposit()- std[i].getFine());
				totFine = 0;
			}
		}
		
		
		
	}
	

	@Override
	public void deleteStudy(StudyVO[] std) {
		System.out.println(">>탈퇴<<");
		System.out.print("회원번호 : ");
		String memberCode = scan.nextLine();
		
		if(cnt > 0) {
			for (int i = 0; i < cnt; i++) {
				
				if(std[i].getMemberCode().equals(memberCode)) {
					std[i].setMemberCode(deleteMem);
				}
				
			}
		}
		
	}

	@Override
	public void outputFine(StudyVO[] std) {
		for (int i =0; i < cnt; i++) {
			if(std[i].getFine() == 0) {
				
			} else {
				System.out.printf("%4s %5s %7s %5d", 
						std[i].getMemberCode(), 
						std[i].getMemberName(),
						std[i].getStudyDate(), 
						std[i].getFine());
				System.out.println("\n----------------");	
			}
		}

	}

	@Override
	public void outputStudy(StudyVO[] std) {
		for(int i=0; i< cnt; i++) {
			if(deleteMem.equals(std[i].getMemberCode())) {
				
				
			} else {
				System.out.printf("%5s %5s %6d %6s %6s %6s %6s %6s %5d %5d" 
						, std[i].getMemberCode()
						, std[i].getMemberName()
						, std[i].getDeposit()
						, std[i].getStudyDate()
						, std[i].getChapter()
						, std[i].getTask()
						, std[i].getChk1()
						, std[i].getChk2()
						, std[i].getFine()
						, std[i].getBalance()
						
						);
				System.out.println("\n----------------");		
			}
		}

	}

}



```

<br>


<StudyMain.java>

```java

package studyProgram;

import java.util.Scanner;

public class StudyMain {
	final static int SIZE = 100;
	
	public static void main(String[] args) {
		
		StudyInfoIm info = new StudyInfoIm();
		StudyVO std[] = new StudyVO[SIZE]; 
		
		int menu;
		
		while(true) {
			
			menu();
			
			Scanner scan = new Scanner(System.in);
			
			menu=scan.nextInt();
			System.out.println();
			
			switch(menu) {
			case 1:
				join(info,std);
				break;
			case 2:
				input(info,std);
				break;
			case 3:
				update(info,std);
				break;
			case 4: 
				delete(info,std);
				break;
			case 5:
				outputFine(info,std);
				break;
			case 6:
				outputStudy(info,std);
				break;
			default:
				System.out.println("메뉴를 다시 선택하세요!!\n");
				
				
			}
			
		}
		
	}
	
	static void menu() {
		
		System.out.println("메뉴");
		System.out.println("1.스터디가입");
		System.out.println("2.정보입력");
		System.out.println("3.정보수정");
		System.out.println("4.스터디탈퇴");
		System.out.println("5.벌금현황");
		System.out.println("6.스터디현황");
		System.out.println("7.종료");
		System.out.println();
	}
	
	
}



```

<br>

<StudyVO.java>

```java

package studyProgram;

public class StudyVO {
	
	
	private String memberCode; //회원번호
	private String memberName; //
	private String joinDate;
	private int deposit;
	
	
	private String studyDate;
	private String chapter;
	private String task;
	private String chk1;
	private String chk2;
	
	private int fine;
	private int balance;
	
	

	public String getMemberCode() {
		return memberCode;
	}
	public void setMemberCode(String memberCode) {
		this.memberCode = memberCode;
	}
	public String getMemberName() {
		return memberName;
	}
	public void setMemberName(String memberName) {
		this.memberName = memberName;
	}
	public String getJoinDate() {
		return joinDate;
	}
	public void setJoinDate(String joinDate) {
		this.joinDate = joinDate;
	}
	public int getDeposit() {
		return deposit;
	}
	public void setDeposit(int deposit) {
		this.deposit = deposit;
	}
	public String getStudyDate() {
		return studyDate;
	}
	public void setStudyDate(String studyDate) {
		this.studyDate = studyDate;
	}
	public String getChapter() {
		return chapter;
	}
	public void setChapter(String chapter) {
		this.chapter = chapter;
	}
	public String getTask() {
		return task;
	}
	public void setTask(String task) {
		this.task = task;
	}
	public String getChk1() {
		return chk1;
	}
	public void setChk1(String chk1) {
		this.chk1 = chk1;
	}
	public String getChk2() {
		return chk2;
	}
	public void setChk2(String chk2) {
		this.chk2 = chk2;
	}
	public int getFine() {
		return fine;
	}
	public void setFine(int fine) {
		this.fine = fine;
	}
	public int getBalance() {
		return balance;
	}
	public void setBalance(int balance) {
		this.balance = balance;
	}
	
	
	@Override
	public String toString() {
		return "StudyVO [memberCode=" + memberCode 
				+ ", memberName=" + memberName 
				+ ", joinDate=" + joinDate 
				+ ", deposit=" + deposit 
				+ ", studyDate=" + studyDate
				+ ", chapter=" + chapter
				+ ", task=" + task
				+ ", chk1=" + chk1
				+ ", chk2=" + chk2
				+ ", fine=" + fine
				+ ", balance=" + balance
				+ "]"
				;
				
	}
	
	
}


```


