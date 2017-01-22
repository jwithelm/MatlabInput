# HebiJoystick

HebiJoystick is joystick input library for MATLAB that serves as a mostly drop-in replacement for [vrjoystick](https://www.mathworks.com/help/sl3d/vrjoystick.html). It is intended for people who don't have access to the [3D Animation Toolbox](https://www.mathworks.com/products/3d-animation.html). 

## Notes

* The order of axes and buttons may be different from vrjoystick
* The order of axes and buttons may differ between operating systems
* There is a maximum number of events that can occur between reads. If reads don't happen frequently enough, the returned state may not match the real physical state. A polling rate of about once per second should be sufficient for the default settings.

## Installation

* Download the [latest release](https://github.com/HebiRobotics/HebiJoystick/releases)
* Extract the .zip file into a folder of your choice
* Add the unzipped files to the [MATLAB path](http://www.mathworks.com/help/matlab/ref/path.html)

## Usage

Create joystick and react to button presses.

```matlab
joy = HebiJoystick(1);
while true
  [axes, buttons, povs] = read(joy);
  if any(buttons)
    disp('one or more buttons are pressed down');
  end
  pause(0.1);
end
```

See [vrjoystick](https://www.mathworks.com/help/sl3d/vrjoystick.html) documentation for more information.

![comparison](https://github.com/HebiRobotics/HebiJoystick/raw/resources/comparison.png)



