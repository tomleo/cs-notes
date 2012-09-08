=============
C# Notes
=============

Exception Handling
==================

try {
//
} catch(Exception e) {
  Console.WriteLine(e.ToString() e.Message e.StackTraace e.Source e.TargetSite );
}

class C_Exception:Application {
  private int my_code_error;
  public C_Exception(int a) { my_code_error = a; }
  public int getErrorCode() { return my_code_error; }
}

throw new C_Exception(-5);
