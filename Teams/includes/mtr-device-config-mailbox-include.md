
Vous pouvez améliorer votre expérience de réunion salles Teams en personnalisant la façon dont le compte de ressources répond aux invitations à la réunion et les traite. À l’aide de Exchange Online PowerShell, vous pouvez définir les propriétés de compte de ressource suivantes :

- **AutomateProcessing : `AutoAccept`** Les organisateurs de la réunion reçoivent la décision de réservation de salle directement sans intervention humaine.

- **AddOrganizerToSubject : `$false`** L’organisateur de la réunion n’est pas ajouté à l’objet de la demande de réunion.

- **DeleteComments : `$false`** Conservez le texte dans le corps du message des demandes de réunion entrantes. Cela est nécessaire pour traiter les réunions teams externes et tierces afin de fournir une expérience one touch join.

- **DeleteSubject : `$false`** Conservez l’objet des demandes de réunion entrantes.

- **ProcessExternalMeetingMessages : `$true`** Spécifie s’il faut traiter les demandes de réunion provenant de l’extérieur de l’organisation Exchange. Requis pour les réunions Teams externes et [les réunions tierces](/microsoftteams/rooms/third-party-join).

- **RemovePrivateProperty : `$false`** Garantit que l’indicateur privé qui a été envoyé par l’organisateur de la réunion dans la demande de réunion d’origine reste tel que spécifié.

- **AddAdditionalResponse : `$true`** Le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion.

- **AdditionalResponse : « Il s’agit d’une salle de réunion Microsoft Teams ! »** Texte supplémentaire à ajouter à la réponse d’acceptation de la réunion.

Pour configurer ces propriétés, vous devez vous connecter à Exchange Online PowerShell. Pour plus d’informations, consultez [Se connecter à Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true).

Une fois que vous êtes connecté à Exchange Online PowerShell, vous pouvez configurer les propriétés de boîte aux lettres sur un compte de ressource à l’aide de l’applet de commande [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

L’exemple suivant définit les propriétés du compte de `ConferenceRoom01` ressource :

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

