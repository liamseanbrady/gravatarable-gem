## Simple Gravatar Images

#### Two Steps

- Include the code below in the model that you want to have a **gravatar image**. Note: your column **can be named anything** as long as it **contains an email address**.

```ruby
class User < ActiveRecord::Base
  ...

  gravatar_column :email_address  # pass in name of column which includes email address

  ...
end
```

- This **simple method call** will give you a **user's Gravatar image**.

```erb
<img src="#{@user.gravatar_url}">
```

- **Don't worry** if the value in the **email column changes**. Gravatarable will **change the url** along with it. However, **Gravatarable is super lazy**. It only springs into action when the column that contains the email address changes - it doesn't take CPU time when it doesn't need to. **Awesome!**