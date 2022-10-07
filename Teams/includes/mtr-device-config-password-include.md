
Comme n’importe quel compte Microsoft 365, le mot de passe d’un compte de ressource nouvellement créé est défini pour expirer automatiquement après un certain temps. Toutefois, si le mot de passe du compte de ressource expire, l’appareil salles Teams dans lequel il est connecté ne peut pas se reconnecter à la date d’expiration. 

Pour éviter d’avoir à réinitialiser le mot de passe du compte de ressource, puis à se reconnecter à chaque appareil salles Teams, vous pouvez désactiver l’expiration du mot de passe pour le compte.
  
> [!NOTE]
> La définition **du mot de passe n’expire jamais** est obligatoire pour les appareils Microsoft Teams partagés. Si vos règles de domaine interdisent les mots de passe qui n’expirent pas, vous devez créer une exception pour chaque compte de ressource d’appareil Teams.

Suivez les étapes décrites dans l’un des onglets suivants pour désactiver l’expiration du mot de passe :

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

Tout d’abord, connectez-vous à Active Directory PowerShell :

```PowerShell
   Connect-AzureAD
```

Ensuite, consultez [Définir un mot de passe pour qu’il n’expire jamais](/microsoft-365/admin/add-users/set-password-to-never-expire#set-a-password-to-never-expire).

Cet exemple montre comment définir le mot de passe du compte ConferenceRoom01@contoso.com pour qu’il n’expire jamais.

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1.0**](#tab/azure-active-directory1-password/)

 1. Connectez-vous à MSOnline PowerShell :

       ```PowerShell
       Connect-MsolService
       ```

       Pour plus d’informations sur Active Directory, consultez [Azure Active Directory (MSOnline).](/powershell/azure/active-directory/overview?view=azureadps-1.0&preserve-view=true)

2. Définissez le mot de passe pour qu’il n’expire jamais à l’aide de la syntaxe suivante :

    ```PowerShell
    Set-MsolUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    Cet exemple montre comment définir le mot de passe du compte ConferenceRoom01@contoso.com pour qu’il n’expire jamais.

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```

#### <a name="active-directory-on-premises"></a>[**Active Directory (local)**](#tab/active-directory1-password/)

1. Connectez-vous à Active Directory PowerShell :

    ```PowerShell
       Import-Module ActiveDirectory
    ```
    
    Pour plus d’informations sur Active Directory PowerShell, consultez [ActiveDirectory](/powershell/module/activedirectory).

2. Définissez le mot de passe pour qu’il n’expire jamais à l’aide de la syntaxe suivante :

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    Cet exemple montre comment définir le mot de passe du compte ConferenceRoom01@contoso.com pour qu’il n’expire jamais.

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---