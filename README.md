Configuration
```neon
mails:
	identities:
		default:
			email: example@example.com
			name: Example

		example: Example <example@example.com>

	directories:
		- %appDir%/mails # default
```

app/mails/registration.latte
```latte
{* @event UserFactory::onCreate $user *}
{subject}Welcome to our site {$user}{/subject}
{body text} {* text is default *}
Oh how we are so grateful {$user->name} that you decided to join our awesome service.

Sincerly,
yours CEO
Only Man in the Company
{/body}
{body html}
<marquee>Oh how we are so grateful {$user->name} that you decided to join our awesome service.<marquee>

<p>
	Sincerly,<br />
	yours <strong>CEO</strong><br />
	Only Man in the Company
</p>
{/body}
```
