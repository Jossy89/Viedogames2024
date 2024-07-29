/// @description Inserte aquí la descripción
// Puede escribir su código en este editor

// Create Event of obj_player
if (os_type == os_ios || os_type == os_android) {
    global.mobile = true;
} else {
    global.mobile = false;
}

// Step Event of obj_player
if (global.mobile) {
    // Mobile controls
    var touch = device_mouse_check_button_pressed(0, mb_left);
    if (touch) {
        // Implement touch controls
        // E.g., move player towards touch point
        var tx = device_mouse_x(0);
        var ty = device_mouse_y(0);
        move_towards_point(tx, ty, 5);
    }
} else {
    // PC controls
    if (keyboard_check(vk_left)) {
        x -= 5;
    }
    if (keyboard_check(vk_right)) {
        x += 5;
    }
    if (keyboard_check(vk_up)) {
        y -= 5;
    }
    if (keyboard_check(vk_down)) {
        y += 5;
    }
}
