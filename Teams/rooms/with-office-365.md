---
title: Créer des comptes de ressources pour les salles et les appareils Teams partagés
ms.author: czawideh
author: cazawideh
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
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lisez cet article pour plus d’informations sur la création de comptes de ressources pour les salles et appareils partagés, notamment les Salles Microsoft Teams, les salles Teams sur Surface Hub et la Teams d’écran.
ms.openlocfilehash: e7525a9e9ec6737bab18de4351675d567b61611b
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514545"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>Créer et configurer des comptes de ressources pour des salles et des appareils Teams partagés

Cet article décrit les étapes de création de comptes de ressources pour les espaces et appareils partagés, ainsi que les étapes de configuration des comptes de ressources pour Salles Microsoft Teams sur Windows, salles Teams sur Android, salles Teams sur Surface Hub et les procédures de désenchement hot-king sur Teams  s’affiche.

Microsoft 365 les comptes de ressources sont des Teams boîtes aux lettres et des comptes dédiés à des ressources spécifiques, telles qu’une salle ou un projecteur. Ces comptes de ressources peuvent répondre automatiquement aux invitations aux réunions à l’aide de règles que vous définissez lors de leur création. Par exemple, si vous avez une ressource commune telle qu’une salle de conférence, vous pouvez configurer un compte de ressource pour cette salle de conférence qui acceptera ou refusera automatiquement les invitations aux réunions en fonction de la disponibilité de son calendrier.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> **Skype Entreprise** <br><br>
> Si vous avez besoin d’activer l’utilisation de votre compte de ressource Skype Entreprise, voir [Déployer Salles Microsoft Teams’Skype Entreprise Server](with-skype-for-business-server-2015.md)

## <a name="before-you-begin"></a>Avant de commencer

### <a name="requirements"></a>Conditions requises

Selon votre environnement, vous avez besoin d’un ou plusieurs rôles pour créer des comptes de ressources.

|**Environnement**|**Rôles requis**|
|-----|-----|
|Azure Active Directory  <br/> |Administrateur général ou administrateur utilisateur  <br/> |
|Active Directory  <br/> |Active Directory Enterprise administrateurs de domaine ou ont des droits délégués pour créer des utilisateurs. Azure Active Directory Connecter droits de synchronisation.  <br/> |
|Exchange Online  <br/> |Administrateur général ou administrateur Exchange groupe   <br/> |
|Exchange Server  <br/> |Exchange de l’organisation ou de la gestion des destinataires   <br/> |

Si vous créez des comptes de ressources pour salles Teams, le upN doit correspondre à l’adresse SMTP du compte de ressource. Consultez [les Salles Microsoft Teams requises](requirements.md) avant de déployer salles Teams.

### <a name="what-license-do-you-need"></a>De quelle licence avez-vous besoin ?

Avant de créer un Microsoft 365 de ressources, vérifiez le type de licence dont il a besoin :

- **Teams** Réunions Si vous voulez associer le compte de ressource à un appareil partagé (par exemple, une salle Microsoft Teams ou un écran Teams avec entrées d’accès à l’écran) et l’utiliser pour participer à une réunion Teams afin que les participants peuvent l’utiliser pour présenter des fichiers vidéo et audio, vous avez besoin d’une licence Salle de réunion. Pour plus d’informations sur la gestion des licences pour les salles de réunion, [voir Teams Salle de réunion licences.](rooms-licensing.md)

- **Appels PSTN** Si vous souhaitez que la ressource passe ou reçoit des appels vers ou depuis un numéro de téléphone externe (appelé un réseau téléphonique commuté public ou un appel RST), vous avez besoin d’une licence Microsoft 365 Système téléphonique ou Microsoft 365 Business Voice public. Il vous suffit d’effectuer l’étape 1 de la vue d’ensemble suivante. Consultez ensuite Microsoft Teams [licences de module complémentaire pour](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) plus d’informations.

- Si vous n’utilisez un compte de ressource que pour réserver une ressource, invitez la ressource à votre réunion et demandez-lui d’accepter ou de refuser automatiquement l’invitation&mdash; que vous n’avez pas besoin d’attribuer une licence au compte de ressource. Il vous suffit d’effectuer&mdash; l’étape 1 de la vue d’ensemble suivante.  

## <a name="overview"></a>Présentation

**Étape 1 : créer** [un compte de ressource](#create-a-resource-account). Ou, si une boîte aux lettres de salle existe déjà et que vous souhaitez la convertir en compte de ressource, vous pouvez modifier une boîte aux lettres de salle existante [Exchange de réunion](?tabs=existing-account#create-a-resource-account).

**Étape 2 -**  Ensuite, [configurez votre compte pour](#configure-mailbox-properties) Teams réunions.

**Étape 3 :**  Si le compte de ressource doit être associé à un appareil partagé, par exemple un appareil Teams avec la désactivation de l’accès par défaut, désactivation de [l’expiration du mot de passe](#turn-off-password-expiration).

**Étape 4 -**  Enfin, [attribuez une licence de salle de](#assign-a-meeting-room-license) réunion afin que le compte puisse accéder Microsoft Teams.

Après avoir créé et configuré vos comptes de ressources, consultez [](#next-steps) les étapes suivantes pour passer en revue les tâches de configuration supplémentaires, notamment les groupes de distribution, les fonctionnalités réseau et les appels.

## <a name="create-a-resource-account"></a>Créer un compte de ressource

> [!TIP]
> Lors de l’attribution d’un nom à vos comptes de ressources, nous vous recommandons d’utiliser une convention d’affectation de noms standard au début de l’adresse de courrier. Cela vous aidera à créer des groupes dynamiques pour faciliter la gestion dans Azure Active Directory. Par exemple, vous pouvez utiliser « mtr- » pour tous les comptes de ressources qui seront associés à Salles Microsoft Teams.

> [!TIP]
> Nous vous recommandons de créer tous les comptes de ressources à l’Exchange Online et Azure Active Directory.

Créez un compte de ressource à l’aide d’une méthode dans l’un des onglets suivants :

#### <a name="in-microsoft-365-admin-center"></a>[**Dans Centre d'administration Microsoft 365**](#tab/m365-admin-center)

1. Connectez-vous au Centre d’administration Microsoft 365.

2. Fournissez les informations d’identification d’administrateur pour Microsoft 365 client.

3. Dans le **panneau** gauche, sélectionnez Salles et **& matériel**. Si ces options ne sont pas disponibles dans le panneau gauche, vous devrez peut-être sélectionner **Afficher tout d’abord** .

4. **Sélectionnez Ajouter une boîte aux lettres de ressource** pour créer un compte de salle. Entrez un nom d’affichage et une adresse de messagerie pour le compte, **sélectionnez** Ajouter, puis sélectionnez **Fermer**.

5. Par défaut, les comptes de ressources sont configurés avec les paramètres suivants :

    - Autoriser les réunions répétées
    - Refuser automatiquement les réunions en dehors des limites suivantes
      - Fenêtre de réservation (jours) : 180
      - Durée maximale (heures) : 24
    - Accepter automatiquement les demandes de réunion

    Si vous voulez les modifier, sélectionnez Définir les **options de** planification avant de sélectionner **Fermer**. Si vous souhaitez les modifier ultérieurement, dans **ResourcesRooms** >  **& ressources**, sélectionnez le compte de ressource. Sous Options **de réservation**, sélectionnez **Modifier**.

6. Sélectionnez **la salle** **usersActivez-la** >  et sélectionnez la salle que vous avez créée pour ouvrir le panneau de propriétés.

7. Affectez ensuite un mot de passe au compte de ressource. Dans le panneau, sélectionnez **Réinitialiser le mot de passe**.
 
8. Demander aux utilisateurs de modifier le mot de passe sur un appareil partagé entraîne des problèmes de se connecte. **Décochez l’étape Demander à cet utilisateur de modifier son** mot de passe lors de sa première se connectant, puis sélectionnez **Réinitialiser**.

9. Dans la section **Licences et applications**, définissez l’emplacement de sélection du pays ou de la région d’installation de l’appareil. Sélectionnez ensuite la licence à attribuer, par exemple, Salle de réunion, puis **sélectionnez Enregistrer les modifications**. La licence peut varier en fonction de votre organisation.

Pour modifier les paramètres de la boîte aux lettres de ressources, voir Configurer les propriétés de la boîte aux [lettres](#configure-mailbox-properties) ou utiliser le Exchange d’administration.

Vous devrez peut-être également appliquer des stratégies de bande passante ou de réunion à ce compte. Pour plus [d’informations](#next-steps) , voir la procédure suivante.

#### <a name="with-exchange-online"></a>[**Avec les Exchange Online**](#tab/exchange-online)

1. Connecter à [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

    ``` PowerShell
    Connect-ExchangeOnline
    ```

2. Par défaut, les boîtes aux lettres de salle n’ont pas de comptes associés. Ajoutez un compte lorsque vous créez une boîte aux lettres de salle afin qu’elle puisse s’authentifier auprès Microsoft Teams.

    Si vous créez une boîte aux lettres de ressources :
    
    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```
    
    Cet exemple crée une boîte aux lettres de salle avec les paramètres suivants :

        - Account: ConferenceRoom01@contoso.com
          
        - Name: ConferenceRoom01
        
        - Alias: ConferenceRoom01
        
        - Account password: P@$$W0rd5959

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```

Si vous n’êtes pas dans une configuration hybride Exchange, vous pouvez continuer à l’étape suivante (Configurer les propriétés de boîte [aux lettres](#configure-mailbox-properties)).

Si vous avez une configuration hybride Exchange, vous devez ajouter une adresse de messagerie pour votre compte de domaine local. Pour [plus d’informations, voir Synchroniser des annuaires Office 365 comptes](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78) d’utilisateurs locaux et locaux.

#### <a name="with-exchange-server"></a>[**Avec Exchange Server**](#tab/exchange-server)

  1. Connecter à Exchange Management Shell. [Ouvrez Exchange Management Shell](/powershell/exchange/exchange-server/open-the-exchange-management-shell) ou [connectez-vous à votre serveur Exchange à l’aide de Remote PowerShell](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

   2. Pour créer une boîte aux lettres de salle :

      ``` PowerShell
      New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
      ```
     
   Cet exemple crée une boîte aux lettres de salle avec les paramètres suivants :

   - Compte : ConferenceRoom01@contoso.com
  
   - Nom : ConferenceRoom01

   - Alias : ConferenceRoom01

   - Mot de passe de compte : P@$$W 0rd5959

   ``` PowerShell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
   ```

#### <a name="modify-an-existing-exchange-room-mailbox"></a>[**Modifier une boîte aux lettres Exchange salle existante**](#tab/existing-account)

Pour modifier une boîte aux lettres de salle existante afin qu’elle devienne un compte de ressource, utilisez la syntaxe suivante :

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

Cet exemple active le compte de la boîte aux lettres de salle existante qui possède la valeur d’alias ConferenceRoom02 et définit le mot de passe sur 9898P@$$W 0rd.

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

Si vous avez une configuration hybride Exchange, vous devez également ajouter une adresse de messagerie pour votre compte de domaine local. Pour [plus d’informations, voir Synchroniser des annuaires Office 365 comptes](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78) d’utilisateurs locaux et locaux.

Pour plus d’informations sur la syntaxe et les paramètres, voir [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) et [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Si vous créez ce compte pour Teams salle sur Surface Hub, vous devez également activer ActiveSync sur ce compte. Cela vous permettra d’envoyer des messages électroniques directement à partir du Surface Hub, que vous pouvez utiliser pour des fonctionnalités telles que Tableau blanc. Pour [plus d’informations, voir Application de stratégies ActiveSync à des comptes d’Surface Hub.)](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts)

---

> [!IMPORTANT]
> Si vous utilisez ce compte de ressource uniquement pour réserver de l’espace et accepter ou refuser automatiquement les invitations, vous avez terminé la mise en place. Si vous utilisez ce compte de ressource pour la fonction d’appel PSTN, consultez les Microsoft Teams [de modules add-on pour](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) déterminer quelle licence elle a besoin.
>
> Ne continuez à la section suivante que si le compte de ressource est pour un salles Teams sur Windows, salles Teams sur Android, salles Teams sur Surface Hub ou un écran de Teams avec les Teams avec la fonction d’accès par accès hot-desking.

## <a name="configure-mailbox-properties"></a>Configurer les propriétés d’une boîte aux lettres

Dans Exchange PowerShell, en ligne ou sur site, configurez les paramètres suivants dans la boîte aux lettres de salle pour améliorer l’expérience de réunion :

- **AutomateProcessing : `AutoAccept`** Les organisateurs de réunion reçoivent directement la décision de réservation de salle sans intervention de la personne.

- **AddOrganizerToSubject : `$false`** L’organisateur de la réunion n’est pas ajouté à l’objet de la demande de réunion.

- **DeleteComments : `$false`** Conservez tout texte dans le corps du message des demandes de réunion entrantes. Cette étape est requise pour traiter les réunions Teams et tierces afin d’offrir une expérience de one touch join.

- **DeleteSubject : `$false`** Conservez l’objet des demandes de réunion entrantes.

- **ProcessExternalMeetingMessages : `$true`** Indique s’il faut traiter les demandes de réunion provenant de l’extérieur Exchange organisation. Requis pour les réunions Teams externes et les [réunions tierces](/microsoftteams/rooms/third-party-join).

- **RemovePrivateProperty : `$false`** Garantit que l’indicateur privé envoyé par l’organisateur de la réunion dans la demande de réunion initiale reste tel que spécifié.

- **AddAdditionalResponse : `$true`** Le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion.

- **Réponse supplémentaire : « Il s’agit d’Microsoft Teams salle de réunion ! »** Texte supplémentaire à ajouter à la réponse d’acceptation de la réunion.

Cet exemple configure ces paramètres sur une boîte aux lettres de salle nommée ConferenceRoom01 :

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

Pour plus d’informations sur la syntaxe et les paramètres, [voir Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

## <a name="turn-off-password-expiration"></a>Désactiver l’expiration des mots de passe

Si le mot de passe du compte de ressource expire, l’appareil ne se connecte pas après la date d’expiration. Le mot de passe doit alors être modifié pour le compte de ressource, puis mis à jour sur chaque appareil. Pour éviter cela, vous pouvez désactiver l’expiration des mots de passe.
  
> [!NOTE]
> La définition **d’un mot de passe n’expire** jamais est une exigence pour les Microsoft Teams appareils partagés. Si vos règles de domaine interdit les mots de passe qui n’expirent pas, vous devez créer une exception pour chaque Teams ressource de l’appareil.

Suivez les étapes de l’un des onglets suivants pour désactiver l’expiration du mot de passe :

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

Tout d’Connecter active Directory PowerShell :

```PowerShell
   Connect-AzureAD
```

Ensuite, consultez [Définir un mot de passe pour qu’il n’expire jamais](/microsoft-365/admin/add-users/set-password-to-never-expire?view=o365-worldwide#set-a-password-to-never-expire).

Cet exemple définit le mot de passe du ConferenceRoom01@contoso.com pour qu’il n’expire jamais.

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1,0**](#tab/azure-active-directory1-password/)

 1. Connecter à MSOnline PowerShell :

       ```PowerShell
       Connect-MsolService
       ```

       Pour plus d’informations sur Active Directory, [voir Azure Active Directory (MSOnline).](/powershell/azure/active-directory/overview?view=azureadps-1.0)

2. Définissez le mot de passe pour qu’il n’expire jamais à l’aide de la syntaxe suivante :

    ```PowerShell
    Set-MsolUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    Cet exemple définit le mot de passe du ConferenceRoom01@contoso.com pour qu’il n’expire jamais.

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```

#### <a name="active-directory-on-premises"></a>[**Active Directory (en local)**](#tab/active-directory1-password/)

1. Connecter à Active Directory PowerShell :

    ```PowerShell
       Import-Module ActiveDirectory
    ```
    
    Pour plus d’informations sur Active Directory PowerShell, voir [ActiveDirectory](/powershell/module/activedirectory/?view=windowsserver2022-ps).

2. Définissez le mot de passe pour qu’il n’expire jamais à l’aide de la syntaxe suivante :

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    Cet exemple définit le mot de passe du ConferenceRoom01@contoso.com pour qu’il n’expire jamais.

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---

## <a name="assign-a-meeting-room-license"></a>Attribuer une licence de salle de réunion

Le compte de ressource a besoin d’Microsoft 365 ou Office 365 licence pour se Microsoft Teams.

> [!NOTE]
> Salles Microsoft Teams Standard et Salles Microsoft Teams Premium sont les deux SDK disponibles pour les appareils de salle de réunion partagées, dont salles Teams. Une licence de salle de réunion est requise pour les Teams’écran avec la mise en attente des réunions. Pour plus d’informations, voir [Teams licences de salle de réunion](rooms-licensing.md).

Pour attribuer des licences à l’Centre d'administration Microsoft 365, voir [Attribuer des licences aux utilisateurs](/microsoft-365/admin/manage/assign-licenses-to-users). Pour attribuer des licences à l Azure AD, consultez l’un des onglets suivants :

#### <a name="active-directory-20"></a>[**Active Directory 2.0**](#tab/active-directory2-license/)


1. Connecter à Azure AD
  
    ```PowerShell
    Connect-AzureAD
    ```

     Pour plus d’informations sur Active Directory, voir [PowerShell Azure Active Directory Graph](/powershell/azure/active-directory/overview?view=azureadps-2.0).
    
2. Affectez un emplacement d’utilisation à votre compte de ressource à l’aide de l’cmdlet `Set-AzureADUser` . Cela détermine les S SKD de licence disponibles.

    Dans cet exemple, l’utilisateur est situé aux États-Unis :

    ```PowerShell
    Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -UsageLocation 'US'
    ```

3. Utilisez ensuite cette liste `Get-AzureADSubscribedSku` pour récupérer la liste des SKT disponibles pour votre organisation Microsoft 365 ou Office 365 service.

    ```PowerShell
    Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
    ```

4. Pour attribuer la licence, `Set-AzureADUser` utilisez l’cmdlet et convertissez l’ID de référence SKU de licence (voir l’étape 2) en objet de type de licence PowerShell. Affectez ensuite cet objet au compte de ressource. Dans l’exemple suivant, l’ID de référence SKU de licence est 6070a4c8-34c6-4937-8dfb-39bbc6397a60 et est affecté au compte conferenceroom01@contoso.com :

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

1. Connecter sur MSOnline PowerShell.

   ```PowerShell
   Connect-MsolService
   ```

    Pour plus d’informations sur Active Directory, [voir Azure Active Directory (MSOnline).](/powershell/azure/active-directory/overview?view=azureadps-1.0)

2.  Affectez un emplacement d’utilisation à votre compte de ressource à l’aide de l’cmdlet `Set-MsolUser` . Cela détermine les S SKD de licence disponibles.

    Dans cet exemple, l’utilisateur est situé aux États-Unis.
    
    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    ```
    
    Vous pouvez ensuite l’utiliser `Get-MsolAccountSku` pour récupérer la liste des SKT disponibles pour votre organisation Microsoft 365 ou Office 365 service.

4. Pour attribuer la licence, utilisez l’cmdlet `Set-MsolUser` . Dans cet exemple, la licence « contoso:MEETING_ROOM » est affectée au compte conferenceroom01@contoso.com :

    ```PowerShell
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
    ```

---

Pour valider la création du compte et l’attribution de licence, connectez-vous à n’importe Teams client à l’aide du compte que vous avez créé.

## <a name="next-steps"></a>Étapes suivantes

### <a name="network-and-bandwidth"></a>Réseau et bande passante

Vous devrez peut-être appliquer des stratégies de réseau, de bande passante ou de réunion personnalisées à ce compte. Pour plus d’informations sur les stratégies réseau et de bande passante, voir [Paramètres de stratégie de réunion pour l’audio & vidéo](/microsoftteams/meeting-policies-audio-and-video). Pour salles Teams, nous vous recommandons de définir la bande passante de la stratégie de réunion à 10 Mbits/s.

À des fins de collaboration, vous PowerPoint les notes en direct, le tableau blanc et les notes partagées. Vous pouvez créer une stratégie de réunion pour ajuster les paramètres des participants et invités pour salles Teams. Par exemple, examinez les paramètres de la salle d’accueil, tels que les participants à qui les participants sont automatiquement admis aux réunions. Pour plus d’informations sur Teams de réunion, voir [Gérer les stratégies de réunion dans Microsoft Teams](/microsoftteams/meeting-policies-overview).

### <a name="calling"></a>Appel

Il n’existe aucune obligation unique d’activer les appels avec des comptes de ressources. Vous activez le compte de ressource pour les appels de la même façon que vous activez un utilisateur ordinaire.

> [!NOTE]
> Nous vous recommandons de éteindre la messagerie vocale pour les appareils partagés en attribuant une stratégie d’appel aux comptes de ressources de l’appareil. Pour [plus d’informations,](../teams-calling-policy.md) voir Les appels et le Teams d’appel.

### <a name="configure-distribution-groups"></a>Configurer des groupes de distribution

Pour organiser les emplacements des salles de réunion, vous pouvez ajouter des comptes de ressources de votre appareil à Exchange groupes de distribution. Par exemple, si vous avez des bureaux dans trois emplacements géographiques différents, vous pouvez créer trois groupes de distribution et ajouter les comptes de ressources appropriés à chaque emplacement. Pour plus d’informations, [voir La liste Créer une salle](/exchange/recipients/room-mailboxes?view=exchserver-2019#create-a-room-list).

## <a name="related-articles"></a>Articles connexes

[Configurer des comptes pour Salles Microsoft Teams](rooms-configure-accounts.md)

[Planifier les Salles Microsoft Teams](rooms-plan.md)

[Déployer les Salles Microsoft Teams](rooms-deploy.md)

[Gérer les Salles Microsoft Teams](rooms-manage.md)

[Salles Microsoft Teams licences](rooms-licensing.md)
