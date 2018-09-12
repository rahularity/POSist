#include <bits/stdc++.h>
using namespace std;

vector<Node> userlist;
vector<int> parent;

string get_current_time(){
	
		time_t rawtime;
		struct tm * timeinfo;
		char buffer[80];

		time (&rawtime);
		timeinfo = localtime(&rawtime);

		strftime(buffer,sizeof(buffer),"%d-%m-%Y %H:%M:%S",timeinfo);
		string str(buffer);

	return str;

}


string get_user_data(){
	string owner_name;
	
	//asking the node's user name
	cout<<"Enter owner name: ";
	cin>>owner_name;
	
	string data = owner_name;
	
	//string owner
	static int id = 0;
	data = data + to_string(id++);
	
	return data;
}

int get_node_number(){
	
	static int id = 0;
	return id++;		
}


class Node{
	private:
		int ownerId;
		string ownerName;
		float value;
		string timestamp;
		string data;
		int nodeNumber;
		string nodeId;
		string refNodeId;
		string childRefNodeId;
		string genesisRefNodeId;
		string hashValue;
		
	public:
		
		void display()
		{
			cout<<"userId is: "<<data<<" time at which the node is made: "<<timestamp<<" node number is: "<< nodeNumber;
		}
		
		
		Node(){}
		
		Node(String owner_name, float values){
			
			//timestamp is stored in the format as 12-09-2018 12:05:40
			timestamp = get_current_time();
			data = get_user_data();
			nodeNumber = get_node_number();
			nodeId = data;
			value = values;
			ownerName = owner_name;
			
		}
};


void creating_the_node(){
	
	
	
		string name;
		float value;
	
		cout<<"enter owner name: ";
		cin>>owner_name;
				
		cout<<" the value of the node: ";
		cin>>value;
		
		Node n(owner_name, value);
		
		int parent_node_no;
		cout<<"enter parent node number ";
		cin>>parent_node_no;
		
		parent[n.owner_id] = parent_node_no;
	
		//At any point of time, the sum of all values of nodes should never be larger than the value of the genesis node
		//sum of the set of the values of sibling should never be grater than the value of the root node
		
	
		int sum=0;
		for( it=userlist.begin();it!=userlist.end();it++){
			user temp=*it;
			if(parent[temp] == parent_node_no){
				sum+=temp.value;
				int parent_node_value = temp.value;
			}
			
			if(parent_node_value - sum > value){
				userlist.push_back(n);
				cout<<"your node number is "<<n.nodeNumber;
			}
			
		}
	
				
	
}


int main() {


	
	vector<Node> ::iterator it;

	while(1){
		int case_no;
		cout<<"press 1 to make a node\nPress 2 to edit a node\nPress 3 to see all the nodes";
		cin>>case_no;
	
	
		switch(case_no){
		
			case 1:
			{
				
				
				
				creating_the_node();
			
				break;
			}
			
			
			case 2:
			{
				int user_node_number;
				cout<<"enter your Node number"<<endl;
				cin>>user_node_number;
				for( it=userlist.begin();it!=userlist.end();it++)
				{
            				user temp=*it;
            				if(temp.nodeNumber == user_node_number){
            					cout<<"your node is found";
            					
            				}
				}
				
				break;
			}
			
			
			case 3:
			{
				cout << "Showing list:  ";
				for( it=userlist.begin();it!=userlist.end();it++)
				{
            				user temp=*it;
            				temp.display();
            				cout<<endl;
				}
			break;
			}
			
		}	
	}
	
}
