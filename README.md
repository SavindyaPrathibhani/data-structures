# data-structures
patient Queue
class PatientQueue{
	Patient[] p;
	int nextIndex;
	PatientQueue(){
		p=new Patient[100];
		nextIndex=0;
		}
	public void enQueue(Patient x){
		p[nextIndex++]=x;
		}
	public void printQueue(){
		System.out.print("{");
		for(int i=0; i<nextIndex; i++){
			System.out.print("["+p[i].id+"-"+p[i].name+"], ");
			}
		System.out.println(nextIndex ==0? "Empty}":"\b\b}");
		}
	public Patient deQueue(){
		Patient p1=p[0];
		for(int i=0; i<nextIndex-1; i++){
			p[i]=p[i+1];
			}
		nextIndex--;
		return p1;
		}
	public int size(){
		return nextIndex;
		}
	public void clear(){
		nextIndex=0;
		}
	
	}
class Patient{
	int id;
	String name;
	 Patient(int id, String name){
		 this.id=id;
		 this.name=name;
		 }
	public String getPatientDetail(){
		return ("["+this.id+"-"+this.name+"]");
		}
	}
class Demo{
public static void main(String args[]){
   PatientQueue queue=new PatientQueue();
   queue.enQueue(new Patient(101,"Amal"));
   queue.enQueue(new Patient(102,"Nimal"));
   queue.enQueue(new Patient(103,"Ramal"));
   queue.enQueue(new Patient(104,"Bimal"));
   queue.printQueue(); //{[101-Amal], [102-Niaml], [103-Ramal], [104-Bimal]}
   Patient firstPatient= queue.deQueue();
   //   System.out.println(firstPatient.getPatientDetail()); //[1001-Amal]
   queue.printQueue(); //{[102-Niaml], [103-Ramal], [104-Bimal]}
	  System.out.println("No of patient of the queue : "+queue.size()); //3
   queue.clear();
   queue.printQueue(); //{Empty}
	  System.out.println("No of patient of the queue : "+queue.size()); //0
	}
}
