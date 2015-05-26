# cpp-current-date
Simple Program For Current Date
#include <ctime>
#include <iostream>
using namespace std;

class Date
{

int         getMonth(time_t timeval){
 struct tm * timeinfo;
 timeinfo = localtime(&timeval);
 return timeinfo->tm_mon + 1;
}

int         getDay(time_t timeval){
 struct tm * timeinfo;
 timeinfo = localtime(&timeval);
 return timeinfo->tm_mday;
}

int         getYear(time_t timeval){
 struct tm * timeinfo;
 timeinfo = localtime(&timeval);
 return timeinfo->tm_year+1900;
}

int         getHour(time_t timeval){
 struct tm * timeinfo;
 timeinfo = localtime(&timeval);
 return timeinfo->tm_hour;
}

int         getMin(time_t timeval){
 struct tm * timeinfo;
 timeinfo = localtime(&timeval);
 return timeinfo->tm_min;
}

int         getSec(time_t timeval){
 struct tm * timeinfo;
 timeinfo = localtime(&timeval);
 return timeinfo->tm_sec;
}

std::string getWeekday(time_t timeval){
  struct tm * timeinfo;
  std::string days[7] = {"SUN","MON","TUE","WED","THU","FRI","SAT"}; 


  timeinfo = localtime(&timeval);

  return days[timeinfo->tm_wday];
};

int main()
{

cout << "\nThe Current Date Is : ";
cout << getMonth(time(0)) << "/" << getDay(time(0)) << "/" << getYear(time(0));

return 0;
}
