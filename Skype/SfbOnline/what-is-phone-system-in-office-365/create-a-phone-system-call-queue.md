---
title: Créer une file d’attente de système téléphonique
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: "Apprenez à configurer le système téléphonique pour les files d'attente d'appels Office 365 (Cloud PBX) afin de recevoir un message d'accueil organisationnel, de la musique d'attente et une redirection des appels vers des téléopérateurs dans des listes de distribution et des groupes de sécurité. Vous pouvez également définir la taille maximale de la file d'attente, le délai d'attente et les options de gestion des appels. "
ms.openlocfilehash: 1952d6d180f5b9662b1e598ceb9d0b8d230640c2
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375148"
---
# <a name="create-a-phone-system-call-queue"></a>Créer une file d’attente de système téléphonique

Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.
  
Les files d’attente des systèmes téléphoniques peuvent fournir :
  
- Un message d'accueil pour l'organisation
    
- Une attente musicale
    
- Redirection d’appels pour appeler les agents dans les groupes de sécurité et les listes de distribution à extension messagerie.
    
- Définir des paramètres pour la taille maximale de file d’attente appel, délai d’expiration et options de gestion des appels.
    
When someone calls in to a phone number that is set up up with a call queue, they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent. The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in the  *First In, First Out*  (FIFO) manner.
  
Tous les appels en attente dans la file d’attente seront distribués à l’aide d’un mode de routage standard ou le mode de routage en série :
  
- Avec le routage standard, le premier appel dans la file d’attente sonnera tous les agents en même temps.
    
- Avec le routage en série, le premier appel dans la file d’attente sonnera chez tous les téléopérateurs un à un.
    
    > [!NOTE]
    > Les téléopérateurs qui sont **déconnectés**, ont défini leur présence sur **Ne pas déranger,** ou ont désactivé la file d’attente ne seront pas appelés.
  
- Une seule notification d'appel entrant (pour l'appel en tête de file) sera envoyée aux téléopérateurs à la fois.
    
- Lorsqu'un téléopérateur accepte l'appel, le prochain appel entrant dans la file d'attente sonnera pour les autres téléopérateurs.
    
## <a name="step-1---getting-started"></a>Étape 1 : prise en main

Avant de commencer à utiliser les files d'attente d'appels, il est impératif de noter les points suivants :
  
- Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license. The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for call queues. The number of call queues you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization. To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
    > To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Pour en savoir plus sur Plans d'Appels Office 365, voir [Quels sont les forfaits d’appels dans Office 365 ?](/microsoftteams/what-are-calling-plans-in-office-365) et [Forfaits d'appels pour Office 365](/microsoftteams/calling-plans-for-office-365).
    
    > [!NOTE]
    > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge en tant que des Agents de file d’attente des appels. 
  
- You can only assign toll and toll-free service phone numbers that you got in the **Skype for Business admin center** or transferred from another service provider to Phone System call queues. To get and use toll-free service numbers, you need to set up Communications Credits.
    
    > [!NOTE]
    > Les numéros de téléphone des utilisateurs (abonnés) ne peuvent pas être attribués à des files d'attente. Seuls les numéros de téléphone gratuits et payants peuvent être utilisés. 
  
- Lorsque vous distribuez les appels entrants à partir d’une file d’attente des appels système téléphonique, ces clients sont pris en charge pour les agents d’appel :
    
  - Client de bureau Skype Entreprise 2016 (versions 32 et 64 bits)
    
  - Client de bureau Lync 2013 (versions 32 et 64 bits)
    
  - All IP phone models supported for Skype for Business Online. See [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).
    
  - Client Mac Skype Entreprise (version 16.8.196 et ultérieures) 
    
  - Client Android Skype Entreprise (version 6.16.0.9 et ultérieures)
    
  - Client iPhone Skype Entreprise (version 6.16.0 et ultérieures)
    
  - Client Mac Skype Entreprise (version 6.16.0 et ultérieures)

  - Client Microsoft Teams Windows (versions 32 et 64 bits)

  - Client Mac Microsoft Teams

  - Application iPhone Microsoft Teams

  - Application Android Microsoft Teams
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Étape 2 : obtention ou transfert de numéros de service gratuits ou payants

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).
  
> [!NOTE]
> If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.
  
## <a name="step-3---create-a-new-call-queue"></a>Étape 3 : création d'une file d'attente d'appels

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**

Dans le **Centre d'administration de Skype Entreprise**, cliquez sur **Routage des appels** > **Files d'attente d'appels**, puis cliquez sur **Ajouter nouveau**:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>Définissez le nom d'affichage de la file d'attente, un numéro de téléphone et un domaine (le cas échéant).

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![Numéro 1](../images/sfbcallout1.png)<br/>
**Nom** Entrez un nom d'affichage descriptif pour la file d'attente d'appels. Le nom est obligatoire et peut contenir jusqu'à 64 caractères, espaces compris.<br/> Ce nom sera affiché dans la notification de l'appel entrant.
***
![Numéro 2](../images/sfbcallout2.png)<br/>**Phone number** Select a service toll or toll-free phone number for the call queue. This is optional. <br/> If there aren't any listed, you need to get service numbers before you can create this call queue. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md)
***
![Numéro 3](../images/sfbcallout3.png)<br/>**Domaine** S'il est disponible, sélectionnez le domaine Office 365 que vous souhaitez utiliser. Ce champ sera uniquement disponible si vous disposez de plusieurs domaine utilisés avec Office 365. Si c'est le cas, vous devez choisir le nom de domaine dans la liste. <br/> Par exemple, le domaine peut se présenter comme suit :  _contoso.com or redmond.contoso.com_
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Définir le message d'accueil et la musique lue pendant la mise en attente

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>**Greeting** is optional. This is the greeting that is played for people who call in to the call queue number. <br/> Vous pouvez télécharger un fichier audio (format .wav, .mp3 ou .wma).
***
![Numéro 2](../images/sfbcallout2.png)<br/>**Musicale** Vous pouvez utiliser la musique par défaut en attente fournie avec la file d’attente de l’appel, ou vous pouvez télécharger un fichier audio .wav ou .wma mp3 formats à utiliser en tant que votre musique personnalisée en attente. 
   

### <a name="select-the-call-distribution-method"></a>Sélectionner la méthode de distribution d’appel

![Indique les options de méthodes de distribution d'appel](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>**Call distribution method** You can choose either **Attendant** or **Serial** for your call queue distribution method. All new and existing call queues will have attendant routing selected by default. To use serial routing, you must explicitly choose the **Serial** routing option in UI and cmdlets. <br/><br/> When serial routing is chosen and the call queue is saved, the calls from the queue will ring your agents one by one, starting from the beginning of the agent list. If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.   

> [!NOTE]
> Ce type de routage passera les agents qui sont **déconnectés**, qui ont réglé leur présence sur **Ne pas déranger** ou ont choisi d'être **exclus** de la réception d'appels depuis cette file d’attente. 
   
### <a name="select-an-agent-opt-out-option"></a>Sélectionner une option d'exclusion d'agent

![Montre la case à cocher d'exclusion de l’agent](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>**Option d'exclusion d'agent** Vous pouvez choisir d’autoriser les téléopérateurs à refuser de prendre des appels à partir d’une file d’attente spécifique en sélectionnant **Option d'exclusion d'agent**.  <br/> Enabling this option allows all agents in this queue to start or stop receiving call from this call queue at will. You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).  <br/><br/> Pour accéder à l’option d'exclusion, les agents peuvent procéder comme suit :
 1. Ouvrir **Options** dans leur client Skype Entreprise de bureau. 
 2. Sous l’onglet **Renvoi d’appel**, cliquer sur le lien **Modifier les paramètres en ligne**.
 3. Dans la page de paramètres utilisateur, cliquer sur **Files d’attente d'appels**, puis désactiver les cases à cocher des files d’attente desquelles ils souhaitent être exclus.
 
    > [!NOTE] 
    > Les agents utilisant les clients Mac, mobile, ou Lync 2013, ou les utilisateurs Hybrid Voice qui sont hébergés localement à l’aide du serveur Skype Entreprise 2015, peuvent aller à [https://aka.ms/cqsettings](https://aka.ms/cqsettings) pour accéder à l’option d'exclusion.
   
### <a name="add-call-agents-to-a-call-queue"></a>Ajouter des téléopérateurs à une file d'attente d'appels

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/><br/>Les téléopérateurs (50 maximum) peuvent être :
* Un utilisateur en ligne avec une licence de **Système téléphonique** et enregistré pour Enterprise Voice ou avec un forfait d'appel. <br/><br/> **Note:**  To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
* Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group. It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue. A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues. Newly created Office 365 Groups are available almost immediately. <br/> 

  > [!NOTE] 
  > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge.           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>Définir la taille maximale de la file d'attente et la durée maximale d'attente

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/><br/>**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time. The default is 50, but it can range from 0 to 200.When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.
***
![Numéro 2](../images/sfbcallout2.png)<br/><br/>**Lorsque le nombre maximal d’appels est atteint.** Lorsque la file d’attente d’appels atteint sa taille maximale (définie à l’aide de la valeur **maximale des appels dans la file d’attente** ), vous pouvez choisir que se passe-t-il au nouvel appel entrant.
* **Déconnexion avec signal Occupé** L'appel sera déconnecté.
* **Transférer cet appel** Lorsque vous choisissez cette option, vous devez ces options :
  * **Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. <br/> <br/>Pour plus d’informations sur les licences requises pour la messagerie vocale, voir [Configurer le système téléphonique de la messagerie vocale](/microsoftteams/set-up-phone-system-voicemail). 
     
    > [!Note]
    > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge.<br/>
     
  * **File d’attente des appels** Vous devez avoir déjà créé une autre file d’attente d’appel, mais une fois que vous le faites, vous pouvez sélectionner cette file d’attente de l’appel.
  * **Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).
***
![Numéro 3](../images/sfbcallout3.png)<br/><br/>**Durée d'attente d'un appel dans la file d'attente** Vous pouvez également décider de la durée maximale pendant laquelle un appel peut être mis en attente avant d'expirer ou d'être redirigé. La destination de redirection est basée sur la définition du paramètre **Lorsqu'un appel expire**. Le délai peut être défini entre 0 et 45 minutes. <br/><br/> The timeout value can be set in seconds, at 15-second intervals. This allows you to manipulate the call flow with finer granularity. For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search Auto Attendant. 

***
![Numéro 4](../images/sfbcallout4.png)<br/><br/>**Lorsqu'un appel expire** Lorsque l'appel atteint la limite définie par le paramètre **Durée d'attente d'un appel dans la file d'attente**, vous pouvez choisir le traitement ultérieur de l'appel en question :
* **Déconnecter** L'appel sera déconnecté.
* **Transférer cet appel** Lorsque vous choisissez cette option, vous devez ces options :
  * **Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. </br><br/>  Pour plus d’informations sur les licences requises pour la messagerie vocale, voir [Configurer le système téléphonique de la messagerie vocale](/microsoftteams/set-up-phone-system-voicemail). 

    > [!Note]
    > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge.<br/>

  * **File d’attente des appels** Vous devez avoir déjà créé une autre file d’attente d’appel, mais une fois que vous le faites, vous pouvez sélectionner cette file d’attente de l’appel.
  * **Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Modifier l'ID de l’appelant de l’utilisateur pour le transformer en numéro de téléphone de la file d’attente

Vous pouvez protéger l’identité d’un utilisateur en créant une stratégie utilisant la commande d'applet **New-CallingLineIdentity**, plutôt qu'en modifiant son ID d’appelant pour les appels sortants vers une file d’attente d’appel.
  
Pour ce faire, exécutez :
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet. To do this, run:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Vous pouvez obtenir plus d’informations sur la façon d’apporter des modifications aux paramètres d’identification de l’appelant dans votre organisation [ici](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="want-to-know-more"></a>Vous souhaitez en savoir plus ?

Vous pouvez également utiliser PowerShell Windows pour créer et configurer des files d'attente.
  
### <a name="call-queue-cmdlets"></a>Applets de commande de file d'attente d'appels

Voici les applets de commande requis pour gérer une file d'attente d'appels.
  
- [Nouvelle-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [Configurer-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [Obtenir-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [Supprimer-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### <a name="more-about-windows-powershell"></a>Informations supplémentaires sur PowerShell Windows

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Rubriques connexes
[Voici les avantages du système téléphonique dans Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams](getting-service-phone-numbers.md)

[Disponibilité des offres d'appels et d'audioconférence selon les régions et les pays](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
