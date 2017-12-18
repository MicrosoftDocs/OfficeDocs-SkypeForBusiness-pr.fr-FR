---
title: "Messages électroniques qui sont envoyés automatiquement aux utilisateurs lorsque leurs paramètres de conférence Audio modifier"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/10/2017
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
description: "Learn about what information is sent automatically to users by email when their dial-in conferencing settings change. "
---

# Messages électroniques qui sont envoyés automatiquement aux utilisateurs lorsque leurs paramètres de conférence Audio modifier

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'avertissement.  
  
Messages électroniques seront automatiquement envoyés aux utilisateurs qui sont [Configurer la conférence Audio pour Skype entreprise et Teams Microsoft](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md) à l'aide de Microsoft comme fournisseur de services d'audioconférence.
  
Par défaut, il existe quatre types de message électronique qui sera envoyé à vos utilisateurs configurés pour les conférences Audio. Toutefois, si vous voulez limiter le nombre de messages électroniques envoyés aux utilisateurs, vous pouvez désactiver. Services d'audioconférence dans Office 365 vous envoie un courrier électronique à vos utilisateurs de messagerie quand :
  
- **Une licence de conférence Audio est affectée à leur ou lorsque vous modifiez le fournisseur de services d'audioconférence à Microsoft.**
    
    Ce message électronique inclut l'ID de conférence, le numéro de téléphone de conférence par défaut pour les réunions, les services d'audioconférence code confidentiel pour l'utilisateur et les instructions et lien pour utiliser le Skype pour entreprise Online réunion outil mises à jour qui permet de mettre à jour les réunions existantes pour la utilisateur. Voir [Attribuez Skype pour les entreprises et Microsoft Teams des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) ou[Affecter Microsoft comme fournisseur de services d'audioconférence](assign-microsoft-as-the-audio-conferencing-provider.md).
    
    > [!NOTE]
    > Si votre organisation a été activée pour les identifiants de conférence dynamique, toutes les réunions d'un utilisateur qu'ils planifient aura identifiants de conférence unique. Vous pouvez configurer [Utilisation d'identificateurs dynamiques audioconférence dans votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Voici un exemple de ce courrier électronique :
    
     ![Skype for Business Verify License](../images/17913e03-8b4a-4563-b58d-2f09b65fbcaa.png)
  
    Vous trouverez plus d'informations sur Skype pour les licences d'entreprise en regardant [Skype pour les entreprises et Microsoft Teams module complémentaire licences](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
- **L'ID de conférence ou le numéro de téléphone par défaut d'une conférence pour un utilisateur change.**
    
    Ce courrier électronique contient l'ID de conférence, numéro de téléphone de conférence par défaut et les instructions et lien pour utiliser le Skype entreprise Online réunion mise à jour outil servant à mettre à jour les réunions existantes pour l'utilisateur. Mais ce courrier électronique n'inclut pas services d'audioconférence de l'utilisateur code confidentiel. Voir [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user.md).
    
    > [!NOTE]
    > Si votre organisation a été activée pour les identifiants de conférence dynamique, toutes les réunions d'un utilisateur qu'ils planifient aura identifiants de conférence unique. Vous pouvez configurer [Utilisation d'identificateurs dynamiques audioconférence dans votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Voici un exemple de ce courrier électronique :
    
     ![Les informations de la conférence rendez-vous ont été modifiées.](../images/d6d3e028-d9fb-48c4-97c0-a73d6ade5ea3.png)
  
- **Les services d'audioconférence code confidentiel d'un utilisateur est réinitialisé.**
    
    Ce courrier électronique contient des services d'audioconférence de l'organisateur code confidentiel, l'ID de conférence existant et numéro de téléphone de conférence par défaut pour l'utilisateur. Voir [Réinitialiser le code confidentiel conférence Audio pour un utilisateur](reset-the-audio-conferencing-pin-for-a-user.md).
    
    > [!NOTE]
    > Si votre organisation a été activée pour les identifiants de conférence dynamique, toutes les réunions d'un utilisateur qu'ils planifient aura identifiants de conférence unique. Vous pouvez configurer [Utilisation d'identificateurs dynamiques audioconférence dans votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Voici un exemple de ce courrier électronique :
    
     ![Le code confidentiel de la conférence rendez-vous a été modifié.](../images/df8df4f8-d11f-41b8-9187-99e66a88831b.png)
  
- **Licence d'un utilisateur est supprimée ou lorsque le fournisseur de services d'audioconférence change de Microsoft autre fournisseur ou aucun.**
    
    Cela se produit lorsque la licence de **Conférence Audio** est supprimée à partir d'un utilisateur ou lorsque vous modifiez le fournisseur de services d'audioconférence d'un utilisateur de Microsoft à un fournisseur de services d'audioconférence tiers ou lorsque vous définissez le fournisseur sur **Aucun**. Ce courrier électronique contient des instructions et des informations pour l'utilisateur à utiliser la Skype pour entreprise Online Meeting Update Tool pour supprimer des informations spécifiques de services d'audioconférence, telles que la valeur par défaut ID de conférence téléphone numéro ou une téléconférence.
    
    Voir [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) ou[Affecter un tiers comme fournisseur de services d'audioconférence](assign-a-third-party-as-the-audio-conferencing-provider.md).
    
    Voici un exemple de ce courrier électronique :
    
     ![La fonctionnalité Conférence rendez-vous est désactivée.](../images/4ebc8ae6-b516-452e-8d27-6177e145daba.png)
  
## Modifier les courriers électroniques qui leur sont envoyés

Vous pouvez apporter des modifications à la messagerie électronique qui est automatiquement envoyé aux utilisateurs, y compris l'adresse de messagerie et le nom d'affichage qui est inclus dans les informations de contact  *à partir de*  . Par défaut, l'expéditeur des e-mails sera d'Office 365, mais vous pouvez modifier l'adresse de messagerie et nom complet à l'aide de Windows PowerShell et l'applet de commande[Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) . Pour apporter des modifications à l'adresse de messagerie qui envoie le message électronique aux utilisateurs, vous devez :
  
- entrer l'adresse électronique dans le paramètre À _SendEmailFromAddress_;
    
- entrer le nom d'affichage associé à l'adresse électronique dans le paramètre  _SendEmailFromDisplayName_.
    
- définir le paramètre  _SendEmailOverride_ sur _True_;
    
Vous pouvez apporter des modifications à la messagerie électronique envoyé aux utilisateurs, telles que l'adresse de messagerie, le message électronique est envoyé à partir d'et le nom d'affichage pour la messagerie, en cours d'exécution :
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
> Si vous souhaitez modifier les informations de l'adresse électronique, vous devez vous assurer que les stratégies de courrier électronique entrant de votre environnement autorisent les messages électroniques provenant de l'adresse personnalisée de l'expéditeur indiquée. > Si vous décidez de remplacer les informations de contact dans le champ  *De*  , vous devez vérifier que les courriers électroniques sont envoyés correctement aux utilisateurs. À cet effet, vous pouvez effectuer un envoi test avec un utilisateur de votre organisation.
  
Vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) pour gérer d'autres paramètres pour votre organisation, notamment la messagerie.
  
## Comment procéder si vous ne souhaitez pas leur envoyer de courriers électroniques ?

Lorsque vous désactivez l'envoi d'e-mails à des utilisateurs, messagerie ne seront pas envoyée même lorsqu'un utilisateur obtient attribué une licence. Dans ce cas, l'ID de conférence, par défaut numéro de téléphone de conférence et, surtout, son code confidentiel audioconférence ne seront pas envoyée à l'utilisateur. Dans ce cas, vous devez indiquer à l'utilisateur en leur envoyant un courrier électronique distinct ou par téléphone.
  
Par défaut, messages électroniques sont envoyés à vos utilisateurs, mais si vous souhaitez empêcher de réception de courrier électronique pour les conférences audio, vous pouvez utiliser la Skype pour le centre d'administration entreprise ou Windows PowerShell.
  
 **À l'aide de la Skype centre d'administration Business**
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans la **Centre d'administration Skype Entreprise**, dans le volet de navigation gauche, accédez à la **conférence Audio** > **paramètres du pont Microsoft**.
    
4. Dans la page **paramètres du pont Microsoft**, activez ou désactivez **Envoyer automatiquement les messages électroniques pour les utilisateurs si leurs paramètres de services d'audioconférence sont modifiés**.
    
5. Cliquez sur **Enregistrer**.
    
 **Utilisation de Windows PowerShell**
  
1. Pour désactiver l'envoi de courrier électronique à tous vos utilisateurs, exécutez la commande suivante :
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

Vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) pour gérer d'autres paramètres pour votre organisation, notamment la messagerie.
  
## Que devez-vous savoir d'autre sur les courriers électroniques ?

- Pour activer sur plus et désactiver automatiquement envoyer des messages à vos utilisateurs, voir [Activer ou désactiver l'envoi de messages électroniques lorsque modifient les paramètres de conférence Audio](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md).
    
- Parfois, les utilisateurs perdent leurs informations audio et vous devez être en mesure de leur envoyer toutes leurs informations audio pour les. Vous pouvez le faire à l'aide de la Skype centre d'administration Business et cliquer sur **Envoyer les informations de conférence par courrier électronique** sous les propriétés de services d'audioconférence pour un utilisateur. Voir[Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-audio-conferencing-information.md). Toutefois, cette information n'inclut pas les services d'audioconférence code confidentiel.
    
    Voici un exemple du courrier électronique qui sera envoyé aux utilisateurs :
    
     ![Courrier électronique de conférence rendez-vous](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Par défaut, l'expéditeur des e-mails sera d'Office 365, mais vous pouvez modifier l'adresse de messagerie et nom complet à l'aide de Windows PowerShell et l'applet de commande [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .
    
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Pourquoi vous devez utiliser Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre de nombreux avantages dans vitesse, simplicité et la productivité sur qu'à l'aide du centre d'administration Office 365, tels que lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps. En savoir plus sur les avantages suivants dans les rubriques suivantes :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). 
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  
## Voir aussi
<a name="MT_Footer"> </a>

#### 

[Activer ou désactiver l'envoi de messages électroniques lorsque modifient les paramètres de conférence Audio](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md)
  
[Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-audio-conferencing-information.md)

