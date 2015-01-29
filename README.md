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

```ruby
<img src="#{@user.gravatar_url}">
```

- **Don't worry** if the value in the **email column changes**. Gravatar will **change the url** along with it. However, **Gravatar is super lazy**. It only changes the url, when the column that contains the email address changes - no matter how many times the other columns are updated. **Awesome!**