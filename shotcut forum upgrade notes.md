

create new TurnKey Linux machine
restore TKLBAM backup
reboot
install docker from docker.com
cd /var/discourse
remove plugins in containers/app.yml
chown -R 101:104 /var/discourse/shared/standalone/postgres_data
./launcher rebuild app


## Templates

Welcome to %{site_name} &mdash; **thanks for starting a new conversation!**

- Please write in English if you can. This way more people can help you better and faster, and other users can also benefit from the information.

- Does the title sound interesting if you read it out loud? Is it a good summary?

- Who would be interested in this? Why does it matter? What kind of responses do you want?

- Include commonly used words in your topic so others can *find* it. To group your topic with related topics, select a category.

For more, [see our community guidelines](%{base_path}/guidelines). This panel will only appear for your first %{education_posts_text}.

## [Welcome to %{title}](#welcome)
An account is required. Please create an account or log in to continue. Do not try to use Shotcut or shot or anything similar in your username, or we will change it.


Thanks for joining %{site_name}, and welcome!

%{new_user_tips}

We believe in [civilized community behavior](%{base_url}/guidelines) at all times.

Enjoy your stay!
