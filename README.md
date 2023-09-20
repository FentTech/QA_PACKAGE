# QA_PACKAGE
import sys
from tomcat import Tomcat

if __name__ == "__main__":

  # Create Tomcat instance
  tomcat = Tomcat()
  
  # Set port number
  tomcat.set_port(8080)

  # Get webapp directory path 
  webapp_dir = "webapp"

  # Create webapp context
  context = tomcat.add_webapp("/", webapp_dir)

  # Start tomcat server
  tomcat.start()
  tomcat.server.await_termination()

  # Stop tomcat server
  tomcat.stop()
  tomcat.server.shutdown()

  sys.exit(0)
