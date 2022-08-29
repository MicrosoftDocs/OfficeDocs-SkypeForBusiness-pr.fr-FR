---
title: Créer des comptes de ressources pour les salles et les appareils Teams partagés
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lisez cet article pour plus d’informations sur la création de comptes de ressources pour les salles et les appareils partagés, notamment les Salles Microsoft Teams, les salles Teams sur Surface Hub et la mise à l’eau à chaud sur les écrans Teams.
ms.openlocfilehash: 45cd61b476f10f673150653144bdb79a47604962
ms.sourcegitcommit: 17f4baf85e1ac6a2af5f5c6ea2d5aae763efd917
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2022
ms.locfileid: "67405156"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>Créer et configurer des comptes de ressources pour les salles et les appareils Teams partagés

Cet article décrit les étapes de création de comptes de ressources pour les espaces partagés et les appareils, ainsi que les étapes de configuration des comptes de ressources pour Salles Microsoft Teams sur Windows, salles Teams sur Android, salles Teams sur Surface Hub et mise à l’eau à chaud sur les écrans Teams.

Les comptes de ressources Microsoft 365 sont des comptes de boîte aux lettres et teams dédiés à des ressources spécifiques, telles qu’une salle ou un projecteur. Ces comptes de ressources peuvent répondre automatiquement aux invitations aux réunions à l’aide de règles que vous définissez lors de leur création. Par exemple, si vous disposez d’une ressource commune telle qu’une salle de conférence, vous pouvez configurer un compte de ressource pour cette salle de conférence qui acceptera ou refusera automatiquement les invitations aux réunions en fonction de sa disponibilité dans le calendrier. 

Chaque compte de ressource est propre à une seule installation Salles Microsoft Teams ou Teams affiche une implémentation à chaud desking.

> [!NOTE]
> Si vous utilisez des panneaux Microsoft Teams, le compte de ressource salles Teams se connecte aux panneaux Teams salles Teams et associés.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> **Skype Entreprise** <br><br>
> Si vous devez activer votre compte de ressource pour qu’il fonctionne avec Skype Entreprise, consultez [Déployer Salles Microsoft Teams avec Skype Entreprise Server](with-skype-for-business-server-2015.md)

## <a name="before-you-begin"></a>Avant de commencer

### <a name="requirements"></a>Conditions requises

Selon votre environnement, vous avez besoin d’un ou de plusieurs rôles pour créer des comptes de ressources.

|**Environnement**|**Rôles requis**|
|-----|-----|
|Azure Active Directory  <br/> |Administrateur général ou administrateur d’utilisateurs  <br/> |
|Active Directory  <br/> |Administrateurs d’entreprise Active Directory, administrateurs de domaine ou disposant de droits délégués pour créer des utilisateurs. Droits de synchronisation Azure Active Directory Connect.  <br/> |
|Exchange Online  <br/> |Administrateur général ou administrateur Exchange   <br/> |
|Exchange Server  <br/> |Gestion de l’organisation Exchange ou gestion des destinataires   <br/> |

Si vous créez des comptes de ressources pour salles Teams, l’UPN doit correspondre à l’adresse SMTP du compte de ressource. Consultez [Salles Microsoft Teams exigences](requirements.md) avant de déployer salles Teams.

### <a name="what-license-do-you-need"></a>De quelle licence avez-vous besoin ?

Avant de créer un compte de ressource Microsoft 365, vérifiez le type de licence dont il a besoin :

- **Réunions Teams** Si vous souhaitez associer le compte de ressource à un appareil partagé, tel qu’une salle Microsoft Teams ou un affichage Teams avec desking à chaud, et l’utiliser pour participer à une réunion Teams afin que les participants puissent l’utiliser pour présenter de la vidéo et de l’audio via celui-ci, vous avez besoin d’une licence de salle de réunion. Pour plus d’informations sur les licences pour les salles de réunion, consultez [Licences de salle de réunion Teams](rooms-licensing.md).

- **Appels RTC** Si vous souhaitez que la ressource effectue ou reçoive des appels vers ou à partir d’un numéro de téléphone externe (appelé réseau téléphonique commuté public ou appel RTC), vous avez besoin d’une licence Microsoft 365 Phone System ou Microsoft 365 Business Voice. Vous devez uniquement effectuer l’étape 1 dans la vue d’ensemble suivante. Consultez ensuite [les licences de module complémentaire Microsoft Teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) pour plus d’informations.

- Si vous utilisez uniquement un compte de ressource pour réserver une ressource&mdash;, invitez la ressource à votre réunion et demandez-lui d’accepter ou de refuser automatiquement l’invitation&mdash;que vous n’avez pas besoin d’attribuer une licence au compte de ressource et que vous n’avez qu’à effectuer l’étape 1 dans la vue d’ensemble suivante.  

## <a name="overview"></a>Vue d’ensemble

**Étape 1 :** [créer un compte de ressource](#create-a-resource-account). Ou, si une boîte aux lettres de salle existe déjà et que vous souhaitez la convertir en compte de ressource, vous pouvez [modifier une boîte aux lettres de salle Exchange existante](?tabs=existing-account#create-a-resource-account).

**Étape 2 -**  Ensuite, [configurez votre compte](#configure-mailbox-properties) pour les réunions Teams.

**Étape 3 -**  Si le compte de ressource doit être associé à un appareil partagé, tel que Teams s’affiche avec desséchement à chaud, [désactivez l’expiration du mot de passe](#turn-off-password-expiration).

**Étape 4 -**  Enfin, [attribuez une licence de salle de réunion](#assign-a-meeting-room-license) pour que le compte puisse accéder à Microsoft Teams.

Après avoir créé et configuré vos comptes de ressources, consultez [les étapes suivantes](#next-steps) pour passer en revue les tâches d’installation supplémentaires, notamment les groupes de distribution, la fonctionnalité réseau et l’appel.

## <a name="create-a-resource-account"></a>Créer un compte de ressource

> [!TIP]
> Lorsque vous nommez vos comptes de ressources, nous vous recommandons d’utiliser une convention d’affectation de noms standard au début de l’adresse de messagerie. Cela vous aidera à créer des groupes dynamiques pour faciliter la gestion dans Azure Active Directory. Par exemple, vous pouvez utiliser « mtr- » pour tous les comptes de ressources qui seront associés à Salles Microsoft Teams.

> [!TIP]
> Nous vous recommandons de créer tous les comptes de ressources à l’aide de Exchange Online et d’Azure Active Directory.

Créez un compte de ressource à l’aide d’une méthode à partir de l’un des onglets suivants :

#### <a name="in-microsoft-365-admin-center"></a>[**Dans Centre d'administration Microsoft 365**](#tab/m365-admin-center)

1. Connectez-vous au Centre d’administration Microsoft 365.

2. Fournissez les informations d’identification d’administrateur pour votre locataire Microsoft 365.

3. Accédez à **Ressources** dans le volet gauche, puis sélectionnez **Salles & équipement**. Si ces options ne sont pas disponibles dans le volet gauche, vous devrez peut-être sélectionner **Afficher tout** d’abord.

4. Sélectionnez **Ajouter une ressource** pour créer un compte de salle. Entrez un nom d’affichage et une adresse e-mail pour le compte, sélectionnez **Ajouter**, puis **sélectionnez Fermer**.

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

9. Dans la section **Licences et applications** , **définissez l’emplacement De sélection** sur le pays ou la région où l’appareil sera installé. Sélectionnez ensuite la licence que vous souhaitez attribuer, par exemple salle de réunion, puis **sélectionnez Enregistrer les modifications**. La licence peut varier en fonction de votre organisation.

Pour modifier les paramètres de la boîte aux lettres de ressources, consultez [Configurer les propriétés de la boîte aux lettres](#configure-mailbox-properties) ou utiliser le Centre d’administration Exchange.

Vous devrez peut-être également appliquer des stratégies de bande passante ou des stratégies de réunion à ce compte. Pour plus d’informations, consultez [les étapes suivantes](#next-steps) .

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

Si vous n’êtes pas dans une configuration hybride Exchange, vous pouvez passer à l’étape suivante, [configurer les propriétés de boîte aux lettres](#configure-mailbox-properties).

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
>
> Passez à la section suivante uniquement si le compte de ressource concerne un salles Teams sur Windows, salles Teams sur Android, salles Teams sur Surface Hub ou un affichage Teams avec desserrage à chaud.

## <a name="configure-mailbox-properties"></a>Configurer les propriétés de boîte aux lettres

Dans Exchange PowerShell, en ligne ou localement, configurez les paramètres suivants sur la boîte aux lettres de salle pour améliorer l’expérience de réunion :

- **AutomateProcessing : `AutoAccept`** Les organisateurs de la réunion reçoivent la décision de réservation de salle directement sans intervention humaine.

- **AddOrganizerToSubject : `$false`** L’organisateur de la réunion n’est pas ajouté à l’objet de la demande de réunion.

- **DeleteComments : `$false`** Conservez le texte dans le corps du message des demandes de réunion entrantes. Cela est nécessaire pour traiter les réunions teams externes et tierces afin de fournir une expérience one touch join.

- **DeleteSubject : `$false`** Conservez l’objet des demandes de réunion entrantes.

- **ProcessExternalMeetingMessages : `$true`** Spécifie s’il faut traiter les demandes de réunion provenant de l’extérieur de l’organisation Exchange. Requis pour les réunions Teams externes et [les réunions tierces](/microsoftteams/rooms/third-party-join).

- **RemovePrivateProperty : `$false`** Garantit que l’indicateur privé qui a été envoyé par l’organisateur de la réunion dans la demande de réunion d’origine reste tel que spécifié.

- **AddAdditionalResponse : `$true`** Le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion.

- **AdditionalResponse : « Il s’agit d’une salle de réunion Microsoft Teams ! »** Texte supplémentaire à ajouter à la réponse d’acceptation de la réunion.

Cet exemple configure ces paramètres sur une boîte aux lettres de salle nommée ConferenceRoom01 :

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

Pour obtenir des informations détaillées sur la syntaxe et [les paramètres, consultez Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

## <a name="turn-off-password-expiration"></a>Désactiver l’expiration du mot de passe

Si le mot de passe du compte de ressource expire, l’appareil ne se connecte pas après la date d’expiration. Le mot de passe doit ensuite être modifié pour le compte de ressource, puis mis à jour sur chaque appareil. Pour éviter cela, vous pouvez désactiver l’expiration du mot de passe.
  
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

       Pour plus d’informations sur Active Directory, consultez [Azure Active Directory (MSOnline).](/powershell/azure/active-directory/overview?view=azureadps-1.0)

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
    
    Pour plus d’informations sur Active Directory PowerShell, consultez [ActiveDirectory](/powershell/module/activedirectory/).

2. Définissez le mot de passe pour qu’il n’expire jamais à l’aide de la syntaxe suivante :

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    Cet exemple montre comment définir le mot de passe du compte ConferenceRoom01@contoso.com pour qu’il n’expire jamais.

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---

## <a name="assign-a-meeting-room-license"></a>Attribuer une licence de salle de réunion

Le compte de ressource a besoin d’une licence Microsoft 365 ou Office 365 pour se connecter à Microsoft Teams.

> [!NOTE]
> Salles Microsoft Teams Standard et Salles Microsoft Teams Premium sont les deux références SKU disponibles pour les appareils de salle de réunion partagés, y compris les salles Teams. Une licence de salle de réunion est requise pour les affichages Teams à chaud. Pour plus d’informations, consultez les [licences de salle de réunion Teams](rooms-licensing.md).

Pour attribuer des licences à l’aide de la Centre d'administration Microsoft 365, consultez [Affecter des licences aux utilisateurs](/microsoft-365/admin/manage/assign-licenses-to-users). Pour attribuer des licences à l’aide d’Azure AD, consultez l’un des onglets suivants :

#### <a name="active-directory-20"></a>[**Active Directory 2.0**](#tab/active-directory2-license/)


1. Se connecter à Azure AD
  
    ```PowerShell
    Connect-AzureAD
    ```

     Pour plus d’informations sur Active Directory, consultez [Azure Active Directory PowerShell pour Graph](/powershell/azure/active-directory/overview?view=azureadps-2.0).
    
2. Affectez un emplacement d’utilisation à votre compte de ressources à l’aide de l’applet `Set-AzureADUser` de commande. Cela détermine les références SKU de licence disponibles.

    Dans cet exemple, l’utilisateur se trouve dans le États-Unis (États-Unis) :

    ```PowerShell
    Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -UsageLocation 'US'
    ```

3. Ensuite, utilisez cette option `Get-AzureADSubscribedSku` pour récupérer la liste des références SKU disponibles pour votre organisation Microsoft 365 ou Office 365.

    ```PowerShell
    Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
    ```

4. Pour affecter la licence, utilisez l’applet `Set-AzureADUser` de commande et convertissez l’ID de référence SKU de licence (voir l’étape 2) en objet de type de licence PowerShell. Ensuite, affectez cet objet au compte de ressource. Dans l’exemple suivant, l’ID de la référence SKU de licence est 6070a4c8-34c6-4937-8dfb-39bbc6397a60, et il est affecté au compte conferenceroom01@contoso.com :

    ```PowerShell
    #Create an object for a single license type
    $License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
    $License.SkuId = "6070a4c8-34c6-4937-8dfb-39bbc6397a60" 
       
    #Create an object for a multiple license type
    $Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
       
    #Add the single license object to the multiple license object
    $Licenses.AddLicenses = $License 
       
    #Assign the license to the resource account
    Set-AzureADUserLicense -ObjectId ConferenceRoom01@contoso.com -AssignedLicenses $Licenses
    ```

#### <a name="active-directory-10"></a>[**Active Directory 1.0**](#tab/active-directory1-license/)

1. Connectez-vous à MSOnline PowerShell.

   ```PowerShell
   Connect-MsolService
   ```

    Pour plus d’informations sur Active Directory, consultez [Azure Active Directory (MSOnline).](/powershell/azure/active-directory/overview?view=azureadps-1.0)

2.  Affectez un emplacement d’utilisation à votre compte de ressources à l’aide de l’applet `Set-MsolUser` de commande. Cela détermine les références SKU de licence disponibles.

    Dans cet exemple, l’utilisateur se trouve dans le États-Unis (États-Unis).
    
    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    ```
    
    Vous pouvez ensuite récupérer `Get-MsolAccountSku` une liste de références SKU disponibles pour votre organisation Microsoft 365 ou Office 365.

4. Pour attribuer la licence, utilisez l’applet de `Set-MsolUser` commande. Dans cet exemple, la licence « contoso:MEETING_ROOM » est affectée au compte conferenceroom01@contoso.com :

    ```PowerShell
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
    ```

---

Pour valider la création et l’attribution de licences du compte, connectez-vous à n’importe quel client Teams à l’aide du compte que vous avez créé.

## <a name="next-steps"></a>Étapes suivantes

### <a name="meeting-policies"></a>Stratégies de réunion

Vous devrez peut-être appliquer des stratégies de réseau, de bande passante ou de réunion personnalisées à ce compte. Pour plus d’informations sur les stratégies de réseau et de bande passante, consultez [les paramètres de stratégie de réunion pour la vidéo audio &](/microsoftteams/meeting-policies-audio-and-video). Pour salles Teams, nous vous recommandons de définir la bande passante de la stratégie de réunion sur 10 Mbits/s.

À des fins de collaboration, activez PowerPoint Live, tableau blanc et notes partagées. Il est recommandé d’activer le paramètre de stratégie de réunion « Réunion maintenant dans des réunions privées ». Vous pouvez créer une stratégie de réunion pour ajuster les paramètres des participants et des invités pour salles Teams. Par exemple, passez en revue les paramètres de salle d’attente, tels que les participants à admettre automatiquement aux réunions. Pour plus d’informations sur les stratégies de réunion Teams, consultez [Gérer les stratégies de réunion dans Microsoft Teams](/microsoftteams/meeting-policies-overview).

### <a name="calling"></a>Appel

Il n’existe aucune exigence unique pour activer l’appel avec des comptes de ressources. Vous activez le compte de ressource pour appeler de la même façon que vous activez un utilisateur normal.

> [!NOTE]
> Nous vous recommandons de désactiver la messagerie vocale pour les appareils partagés en affectant une stratégie d’appel aux comptes de ressources d’appareil. Pour plus d’informations, consultez [l’appel et le transfert d’appel dans Teams](../teams-calling-policy.md) .

### <a name="configure-distribution-groups-for-teams-calendar"></a>Configurer des groupes de distribution pour le calendrier Teams

Pour organiser vos emplacements de salle de réunion, vous pouvez ajouter vos comptes de ressources d’appareil aux groupes de distribution Exchange. Par exemple, si vous avez des bureaux dans trois emplacements géographiques différents, vous pouvez créer trois groupes de distribution et ajouter les comptes de ressources appropriés à chaque emplacement. Pour plus d’informations, consultez [Créer une liste de salles](/exchange/recipients/room-mailboxes?view=exchserver-2019#create-a-room-list).

### <a name="configure-places-for-outlook-calendar"></a>Configurer des emplacements pour Calendrier Outlook
Pour que les emplacements de salle de réunion apparaissent dans Outlook Room Finder, vous devez utiliser l’applet de commande Exchange PowerShell Set-Place. Non seulement Set-Place remplir le finder de salle dans Outlook, il vous permet également d’ajouter des métadonnées supplémentaires telles que la capacité de la salle ou le plancher de la construction de la salle est. Pour plus d’informations, consultez [Set-Place](/powershell/module/exchange/set-place).

## <a name="related-articles"></a>Articles connexes

[Configurer des comptes pour Salles Microsoft Teams](rooms-configure-accounts.md)

[Planifier les Salles Microsoft Teams](rooms-plan.md)

[Déployer les Salles Microsoft Teams](rooms-deploy.md)

[Gérer les Salles Microsoft Teams](rooms-manage.md)

[licences Salles Microsoft Teams](rooms-licensing.md)
