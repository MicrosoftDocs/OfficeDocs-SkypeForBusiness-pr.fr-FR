---
title: "Affecter un tiers que le fournisseur de conférence audio"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 77f68ca7-c1cf-40d9-9c23-87a6b2abe9de
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords:
- ms.lync.lac.DialInExportImport
- ms.lync.lac.DialInProvider
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Apprenez à configurer un tiers en tant que votre fournisseur de conférence à distance avec Skype pour les entreprises. "
ms.openlocfilehash: a53a2e63f15aa40eb6a88ab13daba2022b35e3b6
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="assign-a-third-party-as-the-audio-conferencing-provider"></a>Affecter un tiers que le fournisseur de conférence audio

Un fournisseur de conférence audio fournit le *pont de conférence*. Le pont de conférence fournit le numéro de téléphone d’accès à distance, les broches et les ID de conférence pour les réunions qui sont créés. Vous devrez affecter un fournisseur de conférence audio pour les personnes qui vont planifier ou entraîner Skype pour les réunions d’entreprise ou Teams de Microsoft.
  
> [!NOTE]
> Pour les Teams de Microsoft, un utilisateur ne peut pas utiliser un fournisseur de conférence audio de tiers, ils doivent utiliser la conférence Audio dans Office 365, qui définit le fournisseur de conférence audio à Microsoft. 
  
## <a name="steps-to-do-before-you-can-assign-a-third-party-audio-conferencing-provider"></a>Étapes à suivre avant de pouvoir affecter un fournisseur de conférence audio de tiers

1. En fonction de votre plan d’Office 365, vous devrez acheter des licences de module complémentaire **d’Audio conférence** pour les personnes de votre organisation qui vont planifier ou entraîner Skype pour les réunions d’entreprise ou Teams de Microsoft à l’aide d’audioconférence. Pour plus d’informations, reportez-vous à la section [Skype pour les professionnels et les équipes Microsoft module complémentaire Gestionnaire de licences](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. Si vous avez acheté des licences de modules complémentaires **d’Audioconférence** , affectez-les aux personnes de votre organisation qui vont planifier ou de mener des réunions qui utilisent l’audioconférence. Reportez-vous à la section [Affecter un Skype pour les professionnels et les équipes Microsoft des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
    
    > [!NOTE]
    > Si vous attribuez une licence de **Conférence Audio** à un utilisateur **après** que vous les affecter un fournisseur de conférence audio de tiers, cette personne est automatiquement fixée à utiliser à la place de Microsoft comme leur fournisseur de conférence audio ! Dans ce cas, vous devez d’abord supprimer Microsoft comme le fournisseur de conférence audio avant de leur affecter un fournisseur de conférence audio de tiers.
  
3. Rechercher un fournisseur de conférence audio de tierce partie dans [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530). Les contacter pour en savoir plus pour vous aider à configurer avec eux.
    
    Ils présentent :
    
  - **Numéros d’accès à distance (numéro payant)** et les numéros verts, s’ils sont disponibles.
    
  - **ID de conférence** qui sont utilisés pour chaque personne qui planifie les réunions. Certains ACPs appellent ces codes secrets de conférence.
    
    > [!NOTE]
    > Si vous avez fait l’initiale définie pour un ACP tiers mais vous devez maintenant apporter des modifications, au bas de la page **Microsoft Bridge** **Cliquez ici pour configurer un fournisseur de conférence audio de tiers**. 
  
    > [!NOTE]
    > Lorsque vous permettre à une personne pour les conférences audio et les affectez à un fournisseur de conférence audio de tierce partie, les numéros de l’audio et de conférence (codes) sont automatiquement ajoutés à n’importe quel **Nouveau** Skype pour les réunions commerciales en ligne qu’ils créent.
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-a-user"></a>L’affectation d’un fournisseur de conférence audio de tiers à un utilisateur

1. Dans le **Skype pour le centre d’administration Business**, choisissez **les utilisateurs**. Sélectionnez l’utilisateur dans la liste et cliquez sur **Modifier** dans le volet Actions.
    
2. Sur la page de propriétés de l’utilisateur, cliquez sur **les conférences Audio** et entrer ces informations :
    
  - **Nom du fournisseur** Dans la liste, sélectionnez le fournisseur tiers.
    
  - **Numéro d’appel payant par défaut** Cela est nécessaire.
    
  - **Par défaut le numéro d’appel gratuit** Ce ne pas nécessaire.
    
  - **ID de conférence** Ceci est fourni par votre fournisseur de conférence audio.
    
3. Cliquez sur **Enregistrer**.
    
4. Envoyer à chaque personne le code PIN que vous avez reçu à partir du fournisseur de conférence audio. Le code confidentiel peut être requis pour appeler dans en tant que l’organisateur de la conférence téléphonique ou d’un leader.
    
    > [!NOTE]
    > Lorsque vous utilisez un fournisseur de conférence audio de tierce partie, il n’est pas un moyen de vous voir ou de définir des broches pour les organisateurs de la réunion. 
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-many-people-at-the-same-time"></a>Comment affecter un fournisseur de conférence audio de tiers à plusieurs personnes en même temps

1. Dans le **Skype pour le centre d’administration Business**, choisissez **audioconférence** > **pont de Microsoft**. En bas de la page, cliquez sur le lien **que vous souhaitez configurer un fournisseur de conférence audio de tiers à la place, cliquez ici**.
    
    > [!NOTE]
    > Si vous avez fait l’initiale définie pour un ACP tiers mais vous devez maintenant apporter des modifications, au bas de la page de **Pont de Microsoft** , **Cliquez ici pour configurer un fournisseur de conférence audio de tiers**. 
  
2. Dans la page **configurer un fournisseur de conférence audio tiers** , sous **Importer et exporter des utilisateurs**, cliquez sur **Assistant Exportation**et puis suivez les étapes de l' **Assistant Exportation des utilisateurs**. Lorsque vous avez terminé, vous aurez un fichier qui liste les personnes que vous souhaitez configurer pour les conférences audio.
    
3. Envoyer le fichier que vous avez créé à votre fournisseur de conférence audio de tiers. Ils seront ajouter les informations de conférence audio pour les personnes figurant dans le fichier et renvoie ensuite le fichier.
    
4. Vérifiez que le fichier retourné comporte les bonnes informations. Nous avons entendu des instances où tous les utilisateurs non répertoriés dans le fichier obtenu les bonnes informations.
    
5. Sur la **page Configurer une conférence audio du tiers fournisseur**, sous **Importer et exporter des utilisateurs**, cliquez sur **Assistant Importation**, puis suivez les étapes de l' **Assistant d’importation d’utilisateurs**
    
6. Envoyer à chaque personne le code PIN que vous avez reçu à partir du fournisseur de conférence audio. Le code confidentiel peut être requis pour appeler dans en tant que l’organisateur de la conférence téléphonique, ou le leader.
    
    > [!NOTE]
    > Lorsque vous utilisez un fournisseur de conférence audio de tierce partie, il n’est pas un moyen de vous voir ou de définir des broches pour les organisateurs de la réunion. 
  
## <a name="when-to-use-a-third-party-audio-conferencing-provider"></a>Quand utiliser un fournisseur de conférence audio de tiers

Si vous êtes dans un pays ou une région où une conférence Audio dans Office 365 n’est pas disponible, la qualité de service n’est pas idéale en raison de son emplacement ou vous disposez d’un contrat existant avec un fournisseur de conférence audio de tiers, nous vous recommandons d’utiliser un audio tiers fournisseur de la conférence. Dans le cas contraire, il est recommandé que votre fournisseur de conférence audio à l’aide de Microsoft.
  
## <a name="automate-assigning-the-third-party-audio-conferencing-provider-by-using-windows-powershell"></a>Automatiser l’affectation du fournisseur de conférence audio de tiers à l’aide de Windows PowerShell

- Pour gagner du temps ou d’automatiser cette action, vous pouvez utiliser l’applet de commande [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851) .
    
    > [!NOTE]
    > Pour modifier le fournisseur audio de Microsoft, à un fournisseur de conférence audio de tiers, vous devez supprimer Microsoft comme le fournisseur de conférence audio. Pour ce faire, utilisez l’applet de commande [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) .
  
- Pour plus d'informations sur l'utilisation de Windows PowerShell, consultez la rubrique [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise](https://go.microsoft.com/fwlink/?LinkId=525038).
    
## <a name="what-else-do-i-need-to-know"></a>Qu’est-ce que je dois savoir d’autre ?

Une personne de votre organisation ne pouvez utiliser qu’un seul fournisseur de conférence audio. Pour modifier le fournisseur de conférence audio d’une personne à Microsoft, voir [déplacement du fournisseur de conférence audio d’un utilisateur à Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) ou [Affecter de Microsoft en tant que le fournisseur de conférence audio](assign-microsoft-as-the-audio-conferencing-provider.md).
  
## <a name="related-topics"></a>Rubriques connexes

[Configurer la conférence Audio pour Skype entreprise et Teams Microsoft](set-up-audio-conferencing.md)
  
[Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

