---
title: "Affecter un tiers comme fournisseur de services d'audioconférence"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/22/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.DialInExportImport
- ms.lync.lac.DialInProvider
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: 77f68ca7-c1cf-40d9-9c23-87a6b2abe9de
description: "Learn how to set up a third-party as your dial-in conferencing provider with Skype for Business. "
---

# Affecter un tiers comme fournisseur de services d'audioconférence

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](77f68ca7-c1cf-40d9-9c23-87a6b2abe9de.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/77f68ca7-c1cf-40d9-9c23-87a6b2abe9de). 
  
Un fournisseur de services d'audioconférence fournit le  *pont de conférence*  . Le pont de conférence fournit le numéro de téléphone, des codes confidentiels et identifiants de conférence pour les réunions sont créés. Vous devez uniquement affecter un fournisseur de services d'audioconférence aux personnes qui vont planifier ou prospect Skype Entreprise ou Teams Microsoft réunions.
  
> [!NOTE]
> Pour Microsoft Teams, un utilisateur ne peut pas utiliser un fournisseur de services d'audioconférence tiers, ils doivent utiliser les services d'audioconférence dans Office 365, qui définit le fournisseur de services d'audioconférence à Microsoft. 
  
## Étapes à suivre avant de vous pouvez affecter un fournisseur de services d'audioconférence tiers

1. En fonction de votre plan Office 365, vous devrez peut-être acheter des licences **Audioconférence** composant additionnel pour les personnes de votre organisation qui vont planifier ou prospect Skype pour les réunions d'entreprise ou Microsoft Teams à l'aide d'audioconférence. Pour plus d'informations, voir[Skype pour les entreprises et Microsoft Teams module complémentaire licences](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. Si vous avez acheté des licences de composant additionnel de **Conférence Audio**, leur affecter les personnes de votre organisation qui vont planifier ou mener des réunions qui utilisent audioconférence. Voir [Attribuez Skype pour les entreprises et Microsoft Teams des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
    
    > [!NOTE]
    > Si vous affectez une licence de **Conférence Audio** à une personne **après** les affecter un fournisseur de services d'audioconférence tiers, cette personne est automatiquement fixée à utiliser Microsoft comme leur fournisseur de services d'audioconférence à la place ! Dans ce cas, vous devrez d'abord supprimer Microsoft comme fournisseur de services d'audioconférence avant leur affecter un fournisseur de services d'audioconférence tiers.
  
3. Rechercher un fournisseur de services d'audioconférence tiers auprès de [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530). Contactez-la pour lui et découvrez comment faire pour vous aider à configurer avec eux.
    
    Ils vous donneront : 
    
  - **Numéros d'accès (numéro payant)** et numéros gratuits si elles sont disponibles.
    
  - les **codes de la conférence** utilisés pour chaque personne qui planifie les réunions (certains fournisseurs d'audioconférences les appellent « mots de passe » de conférence).
    
    > [!NOTE]
    > Si vous avez terminé l'initiale configurer pour un fournisseur tiers, mais vous devez maintenant apporter des modifications, en bas de la page de **Pont Microsoft** **Cliquez ici pour configurer un fournisseur de services d'audioconférence tiers**. 
  
    > [!NOTE]
    > Lorsque vous permettre à une personne pour les conférences audio et les affectez un fournisseur de services d'audioconférence tiers, les numéros audio et les ID de conférence (codes secrets) est automatiquement ajoutés à toutes les réunions Skype Entreprise Online **Nouveau** qu'ils créent.
  
## Comment faire pour affecter un fournisseur de services d'audioconférence tiers à un utilisateur

1. Dans le **Centre d'administration Skype Entreprise**, sélectionnez **Utilisateurs**. Sélectionnez l'utilisateur dans la liste et cliquez sur **Modifier** dans le volet d'actions.
    
2. Page de propriétés de l'utilisateur, cliquez sur **conférence Audio** et entrez ces informations :
    
  - **Nom du fournisseur**: sélectionnez le fournisseur tiers dans la liste.
    
  - **Numéro payant par défaut** Cela est nécessaire.
    
  - **Par défaut numéro gratuit** C'est ne pas obligatoire.
    
  - **ID de conférence** Ceci est fourni par votre fournisseur de services d'audioconférence.
    
3. Cliquez sur **Enregistrer**.
    
4. Envoyer à chaque personne le code confidentiel que vous avez reçu à partir du fournisseur de services d'audioconférence. Le code confidentiel peut être nécessaire pour appeler en tant que l'organisateur de téléconférence ou les points de suite.
    
    > [!NOTE]
    > Lorsque vous utilisez un fournisseur de services d'audioconférence tiers, il n'est pas un moyen d'afficher ou de définir des codes confidentiels au nom d'organisateurs de la réunion. 
  
## Comment faire pour affecter un fournisseur de services d'audioconférence tiers à de nombreux destinataires en même temps

1. Dans la **Centre d'administration Skype Entreprise**, choisissez **audioconférence** > **pont Microsoft**. Dans la partie inférieure de la page, cliquez sur le lien dans **Si vous voulez configurer un fournisseur de services d'audioconférence tiers à la place, cliquez ici**.
    
    > [!NOTE]
    > Si vous avez terminé l'initiale configurer pour un fournisseur tiers, mais vous devez maintenant apporter des modifications, en bas de la page de **Pont Microsoft** **Cliquez ici pour configurer un fournisseur de services d'audioconférence tiers**. 
  
2. Dans la page **configurer un fournisseur de services d'audioconférence tiers**, sous **Importer et exporter des utilisateurs**, cliquez sur **Assistant Exportation** et puis suivez les étapes de l' **Assistant Exporter des utilisateurs**. Lorsque vous avez terminé, vous avez un fichier qui répertorie les personnes que vous voulez configurer pour les services d'audioconférence.
    
3. Envoyer le fichier que vous avez créé à votre fournisseur de services d'audioconférence tiers. Ils seront ajouter des informations de services d'audioconférence pour les personnes figurant dans le fichier et remettre le fichier que vous.
    
4. Vérifiez que le fichier qui vous a été renvoyé contient les bonnes informations. Nous avons été informés de cas où les renseignements avaient été mal transmis aux personnes répertoriées. 
    
5. Sur la **configuration d'une page de fournisseurs de services d'audioconférence tiers**, sous **Importer et exporter des utilisateurs**, cliquez sur **l'Assistant Importation** et puis suivez les étapes décrites dans l' **Assistant Importer des utilisateurs**
    
6. Envoyer à chaque personne le code confidentiel que vous avez reçu à partir du fournisseur de services d'audioconférence. Le code confidentiel pourrez être amené à appeler dans sous forme de l'organisateur de la téléconférence ou points de suite.
    
    > [!NOTE]
    > Lorsque vous utilisez un fournisseur de services d'audioconférence tiers, il n'est pas un moyen d'afficher ou de définir des codes confidentiels au nom d'organisateurs de la réunion. 
  
## Quand utiliser un fournisseur de services d'audioconférence tiers

Si vous êtes dans un pays ou région où audioconférence dans Office 365 n'est pas disponible, la qualité de service n'est pas correctement en raison de son emplacement, ou si vous avez un contrat existant avec un fournisseur de services d'audioconférence tiers, nous vous recommandons d'utiliser un audio tiers fournisseur de conférence. Dans le cas contraire, nous recommandons d'utiliser Microsoft comme fournisseur de services d'audioconférence.
  
## Affecter automatiquement le fournisseur tiers d'audioconférences à l'aide de Windows PowerShell

- Pour gagner du temps ou automatiser la procédure, vous pouvez utiliser l'applet de commande [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851).
    
    > [!NOTE]
    > Pour remplacer le fournisseur audio à partir de Microsoft par un fournisseur de services d'audioconférence tiers, vous devez supprimer Microsoft comme fournisseur de services d'audioconférence. Pour ce faire, utilisez l'applet de commande [Disable-csonlinedialinconferencinguser n'affiche](https://go.microsoft.com/fwlink/?LinkId=617692 ) .
  
- Pour plus d'informations sur l'utilisation de Windows PowerShell, consultez la rubrique [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise](https://go.microsoft.com/fwlink/?LinkId=525038).
    
## Que dois-je savoir également ?

Une personne de votre organisation peut utiliser uniquement un fournisseur de services d'audioconférence. Pour remplacer le fournisseur de services d'une personne par Microsoft, voir [Déplacement de fournisseur de services d'audioconférence d'un utilisateur à Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) ou[Affecter Microsoft comme fournisseur de services d'audioconférence](assign-microsoft-as-the-audio-conferencing-provider.md).
  
## Rubriques connexes

[Configurer la conférence Audio pour Skype entreprise et Teams Microsoft](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
[Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

