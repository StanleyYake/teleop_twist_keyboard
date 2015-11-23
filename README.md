# teleop_twist_keyboard
Generic Keyboard Teleop for ROS
#Launch
To run: `roslaunch teleop_twist_keyboard teleop_twist_keyboard.launch` change the remap topic name if necessary.

or change to this set your own topic name as 2nd cmd line parameters.

 
 if __name__=="__main__":
-    	settings = termios.tcgetattr(sys.stdin)
-	
-	pub = rospy.Publisher('cmd_vel', Twist)
+    settings = termios.tcgetattr(sys.stdin)
+
+    topic_name = 'cmd_vel'
+    if len(sys.argv) == 2:
+        topic_name = sys.argv[1]
+
+
+	pub = rospy.Publisher(topic_name, Twist)

and run `rosrun teleop_twist_keyboard teleop_twist_keyboard.py your_topic_name`
