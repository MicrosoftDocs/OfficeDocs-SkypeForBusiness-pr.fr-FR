
Chaque Salles Microsoft Teams appareil a besoin de son propre compte de ressources. Le compte de ressource est le compte dans lequel l’appareil salles Teams se connecte et c’est ce que les utilisateurs de votre organisation invitent à réserver la salle Teams.

Lorsque vous créez la boîte aux lettres de ressources, vous pouvez spécifier si vous souhaitez autoriser les réunions périodiques, faire en sorte que la salle accepte automatiquement les invitations, le nombre de jours à venir pour accepter les invitations, et ainsi de suite.

> [!TIP]
> Lorsque vous nommez vos comptes de ressources, nous vous recommandons d’utiliser une convention d’affectation de noms standard au début de l’adresse de messagerie. Cela vous aidera à créer des groupes dynamiques pour faciliter la gestion dans Azure Active Directory. Par exemple, vous pouvez utiliser « mtr- » pour tous les comptes de ressources qui seront associés à Salles Microsoft Teams.

> [!TIP]
> Nous vous recommandons de créer tous les comptes de ressources à l’aide de Exchange Online et d’Azure Active Directory.

Créez un compte de ressource à l’aide d’une méthode à partir de l’un des onglets suivants :

#### <a name="in-microsoft-365-admin-center"></a>[**Dans Centre d'administration Microsoft 365**](#tab/m365-admin-center)

1. Connectez-vous au Centre d’administration Microsoft 365.

2. Fournissez les informations d’identification d’administrateur pour votre locataire Microsoft 365.

3. Accédez à **Ressources** dans le volet gauche, puis sélectionnez **Salles & équipement**. Si ces options ne sont pas disponibles dans le volet gauche, vous devrez peut-être sélectionner **Afficher tout** d’abord.

4. Sélectionnez **Ajouter une ressource** pour créer un compte de ressource. Entrez un nom d’affichage et une adresse e-mail pour le compte, puis **sélectionnez Enregistrer**.

5. Par défaut, les comptes de ressources sont configurés avec les paramètres suivants :

    - Autoriser les réunions répétées
    - Refuser automatiquement les réunions en dehors des limites suivantes
      - Fenêtre Réservation (jours) : 180
      - Durée maximale (heures) : 24
    - Accepter automatiquement les demandes de réunion

    Si vous souhaitez les modifier, **sélectionnez Modifier les options de réservation** avant de sélectionner **Fermer**. Si vous souhaitez les modifier ultérieurement, accédez **aux** > **salles de ressources & équipement**, sélectionnez le compte de ressources. Ensuite, sous **Options de réservation**, **sélectionnez Modifier**.

6. Accédez à **Utilisateurs** > **actifs** et sélectionnez la salle que vous avez créée pour ouvrir le panneau des propriétés.

7. Ensuite, affectez un mot de passe au compte de ressource. Dans le panneau, sélectionnez **Réinitialiser le mot de passe**.

8. L’obligation pour les utilisateurs de modifier le mot de passe sur un appareil partagé entraîne des problèmes de connexion. Décochez **Demander à cet utilisateur de modifier son mot de passe lors de sa première connexion**, puis sélectionnez **Réinitialiser le mot de passe**.

Vous devrez peut-être également appliquer des stratégies de bande passante ou des stratégies de réunion à ce compte. Vous pouvez définir des stratégies de boîte aux lettres dans une étape ultérieure.

#### <a name="with-exchange-online"></a>[**Avec Exchange Online**](#tab/exchange-online)

1. Connectez-vous à [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

    ``` PowerShell
    Connect-ExchangeOnline
    ```

2. Par défaut, les boîtes aux lettres de salle n’ont pas de comptes associés. Ajoutez un compte lorsque vous créez une boîte aux lettres de salle afin qu’il puisse s’authentifier auprès de Microsoft Teams.

    Si vous créez une boîte aux lettres de ressources :

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```

    Cet exemple crée une boîte aux lettres de salle avec les paramètres suivants :

    - Compte : ConferenceRoom01@contoso.com

    - Nom : ConferenceRoom01

    - Alias : ConferenceRoom01

    - Mot de passe du compte : P@$$W 0rd5959

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```

Si vous êtes dans une configuration hybride Exchange, vous devez ajouter une adresse e-mail pour votre compte de domaine local. Pour plus d’informations, consultez [synchroniser les répertoires des comptes d’utilisateurs locaux et Office 365](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78).

#### <a name="with-exchange-server"></a>[**Avec Exchange Server**](#tab/exchange-server)

  1. Connectez-vous à Exchange Management Shell. [Ouvrez Exchange Management Shell](/powershell/exchange/exchange-server/open-the-exchange-management-shell) ou [connectez-vous à votre serveur Exchange à l’aide de PowerShell distant](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

  2. Pour créer une boîte aux lettres de salle :

      ``` PowerShell
      New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
      ```

      Cet exemple crée une boîte aux lettres de salle avec les paramètres suivants :

      - Compte : ConferenceRoom01@contoso.com

      - Nom : ConferenceRoom01

      - Alias : ConferenceRoom01

      - Mot de passe du compte : P@$$W 0rd5959

   ``` PowerShell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
   ```

#### <a name="modify-an-existing-exchange-room-mailbox"></a>[**Modifier une boîte aux lettres de salle Exchange existante**](#tab/existing-account)

Pour modifier une boîte aux lettres de salle existante pour qu’elle devienne un compte de ressource, utilisez la syntaxe suivante :

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

Cet exemple active le compte de la boîte aux lettres de salle existante qui a la valeur d’alias ConferenceRoom02 et définit le mot de passe sur 9898P@$$W 0rd.

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

Si vous êtes dans une configuration hybride Exchange, vous devez également ajouter une adresse e-mail pour votre compte de domaine local. Pour plus d’informations, consultez [synchroniser les répertoires des comptes d’utilisateurs locaux et Office 365](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78).

Pour obtenir des informations détaillées sur la syntaxe et les paramètres, consultez [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) et [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Si vous créez ce compte pour Teams Room sur Surface Hub, vous devez également activer ActiveSync sur ce compte. Cela vous permet d’envoyer des messages électroniques directement à partir du Surface Hub, que vous pouvez utiliser pour des fonctionnalités telles que le Tableau blanc. Pour en savoir plus, consultez [Appliquer des stratégies ActiveSync aux comptes d’appareil (Surface Hub](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts) ).

---

> [!IMPORTANT]
> Si vous utilisez uniquement ce compte de ressource pour réserver de l’espace et accepter ou refuser automatiquement des invitations, vous avez terminé la configuration. Si vous utilisez ce compte de ressource pour l’appel RTC, consultez [les licences de module complémentaire Microsoft Teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) pour déterminer la licence dont il a besoin.
