# Jojo-siwa-Goodbye-
Good idea
user 
jojosiwakids/4666
tge website is gonig be your now
the own will found at out
is System;
using System.Drawing;
using System.Windows.Forms;
using System.Media;

namespace LiveToStay
{
    public class LiveToStayForm : Form
    {
        private Button danceButton;
        private PictureBox dancer;
        private Timer danceTimer;
        private int frame = 0;
        private SoundPlayer player;

        public LiveToStayForm()
        {
            this.Text = "Live to Stay";
            this.Size = new Size(400, 400);

            danceButton = new Button()
            {
                Text = "Dance!",
                Location = new Point(150, 300),
                Size = new Size(100, 40)
            };
            danceButton.Click += DanceButton_Click;
            this.Controls.Add(danceButton);

            dancer = new PictureBox()
            {
                Location = new Point(100, 50),
                Size = new Size(200, 200),
                Image = Properties.Resources.Dancer1, // Add images to project resources
                SizeMode = PictureBoxSizeMode.StretchImage
            };
            this.Controls.Add(dancer);

            danceTimer = new Timer();
            danceTimer.Interval = 500; // Change frame every 0.5 seconds
            danceTimer.Tick += DanceTimer_Tick;

            // Replace with your .wav file path
            player = new SoundPlayer("jojo_song.wav");
        }

        private void DanceButton_Click(object sender, EventArgs e)
        {
            danceTimer.Start();
            player.Play();
        }

        private void DanceTimer_Tick(object sender, EventArgs e)
        {
            frame = (frame + 1) % 2;
            if (frame == 0)
                dancer.Image = Properties.Resources.Dancer1;
            else
                dancer.Image = Properties.Resources.Dancer2;
        }

        [STAThread]
        public static void Main()
        {
            Application.EnableVisualStyles();
            Application.Run(new LiveToStayForm());
        }
    }
} 
and boom is working
