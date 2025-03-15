/*
    SFML : Simple and Fast Multimedia Library
    Graphics.hpp : contains declarations for classes and functions related to 2D graphics
*/
#include <SFML/Graphics.hpp>

using namespace sf;
int main(){

    /*
        RenderWindow : is a class from SFML that represents a window on the screen where you can draw graphics
                     : its contructor get:
                                            1- VideoMode
                                            2- window title
        VideoMode : VideoMode is a class that defines the resolution of the window.
    */
    RenderWindow window(
        VideoMode(1500, 800), 
        "sfml window"
    );


    /*
        This is a function that returns 
            true if the window is open 
            and 
            false if it has been closed. 
            This loop forms the main event loop of the application.
    */
    while (window.isOpen()){

        /*
            Event : is a class that represents an event that has occurred, such as a key press, mouse movement, or window closing.
        */
        Event event;

        /*
            window.pollEvent(event) : This function retrieves the next event from the event queue and stores it in the event variable.
                                        it returns:
                                                    true if an event was retrieved
                                                    and
                                                    false if the event queue is empty.
        */
        while (window.pollEvent(event)) {
            
            /*
                event.type: This accesses the type of the event.
                Event::Closed: This is a constant that represents the event of the window being closed (Ex., by clicking the close button)
            */
            if (event.type == Event::Closed) {
                window.close(); // This function closes the window.
            }
        }

        /*
            This function clears the contents of the window, filling it with a default color (usually black). This is necessary to prepare the window for drawing the next frame.
        */
        window.clear();

        /*
            window.display(): This function displays the contents of the back buffer on the screen. This makes the changes you've drawn visible.
        */
        window.display();
    }
    return 0;
}