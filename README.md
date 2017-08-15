# Big-five-

Consider the following object denition for a mathematical set type for integers and a print
method:
struct intSet {
int *data;
int size;
int capacity;
intSet();
intSet(const intSet&);
~intSet();
intSet(intSet &&is);
intSet &operator=(const intSet &is);
intSet &operator=(intSet &&is);
intSet operator|(const intSet &other); // Set union.
intSet operator&(const intSet &other); // Set intersection.
intSet operator==(const intSet &other); // Set equality.
bool isSubset(intSet s); // True if s is a subset of this set.
bool contains(int e); // True if e is an element of this set.
void add(int e) // Adds int e to this set.
void remove(int e); // Removes int e from this set.
};
std::ostream& operator<<(std::ostream& out, const intSet& is);
You are to implement the undened constructors and destructors for the intSet type. Ad-
ditionally you are to overload the bitwise or, bitwise and, equality, and output operators to
represent set union, set intersection and set equality, and printing a set respectively. You must
also implement the methods isSubset, contains, add, and remove above your methods and
data must follow the rules below.


 Copy constructor and assignment operator must perform a deep copy so that each set
has their own independant set of data.
 Each item in a set is unique, if a call to add passes an integer already in the set nothing
is done.
 Set union returns a new set with all elements from both sets.
 Set intersection returns a new set with all elements that are in both sets.
 Two sets A and B are equal i no element of one is not an element of the other. More
precisely (6 9 x s:t: x 2 A ^ x 62 B) ^ (6 9 x st: x 2 B ^ x 62 A) :
 isSubset(intSet s) returns true if every element in s is an element of the set the
method has been called on, false otherwise.
 contains(int e) returns true if the integer e is an element of the set the method has
been called on, false otherwise.
 After add(int e) is called the integer e must be in the set the method has been called
on.
 After remove(int e) is called the the integer e must not be in the set the method has
been called on.
 The capacity of the set should be initialized to 0 until the rst integer is added at which
point the capacity should be made to be 5. If at any point the capacity is not enough it
should be doubled.
 When reading in a set you should read one line of whitespace-delimited integers from
stdin adding each to the set.
 When printing a set you should rst print a left parenthesis then print each integer
in the set delimited by a comma and a space in ascending order and end with a right
parenthesis. For example the set containing 3, 5, and 2 would be printed as follows:
(2, 3, 5)
