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
ms.openlocfilehash: b8fa32a223ed870c73228debd408fa923355ab3d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23890552"
---
# <a name="create-a-phone-system-call-queue"></a>Créer une file d’attente de système téléphonique

Appel de système téléphonique files d’attente contiennent le message d’accueil qui est utilisés lorsqu’une personne appelle un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la capacité de recherche pour l’agent disponible appel suivant gérer l’appel pendant les personnes qui appel Écoutez une musique d’attente. Vous pouvez créer une seule ligne ou plusieurs files d’attente d’appel pour votre organisation.
  
Les files d’attente des systèmes téléphoniques peuvent fournir :
  
- Un message d'accueil pour l'organisation
    
- Une attente musicale
    
- Redirection d’appels pour appeler les agents dans les groupes de sécurité et les listes de distribution à extension messagerie.
    
- Définir des paramètres pour la taille maximale de file d’attente appel, délai d’expiration et options de gestion des appels.
    
Lorsqu’une personne appelle un numéro de téléphone qui est défini d’une file d’attente de l’appel, ils entendra un message d’accueil premier (si une est configuré), puis ils sera placée dans la file d’attente et attendre le prochain agent appel disponible. L'appelant entendra une musique pendant la mise en attente et les téléopérateurs répondront dans l'ordre d'arrivée des appels ( *premier entré, premier sorti*  ).
  
Tous les appels en attente dans la file d’attente seront distribués à l’aide d’un mode de routage standard ou le mode de routage en série :
  
- Avec le routage standard, le premier appel dans la file d’attente sonnera tous les agents en même temps.
    
- Avec le routage en série, le premier appel dans la file d’attente sonnera chez tous les téléopérateurs un à un.
    
    > [!NOTE]
    > Les téléopérateurs qui sont **déconnectés**, ont défini leur présence sur **Ne pas déranger,** ou ont désactivé la file d’attente ne seront pas appelés.
  
- Une seule notification d'appel entrant (pour l'appel en tête de file) sera envoyée aux téléopérateurs à la fois.
    
- Lorsqu'un téléopérateur accepte l'appel, le prochain appel entrant dans la file d'attente sonnera pour les autres téléopérateurs.
    
## <a name="step-1---getting-started"></a>Étape 1 : prise en main

Avant de commencer à utiliser les files d'attente d'appels, il est impératif de noter les points suivants :
  
- Votre organisation doit avoir (au minimum), une licence entreprise E3 plus **Système téléphonique** ou une licence Enterprise E5. Le nombre de licences utilisateur **Système téléphonique** qui sont assignés affecte le nombre de numéros de service qui sont disponibles pour être utilisés pour les files d’attente de l’appel. Le nombre de files d’attente de l’appel que peut avoir est varie selon le nombre de licences **Système téléphonique** et de **Conférence** qui sont assignés au sein de votre organisation. Pour en savoir plus sur les licences, accédez [ici](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
    > Pour rediriger les appels vers des personnes dans votre organisation en ligne, ils doivent disposer d’une licence de **Système téléphonique** et être activés pour Enterprise Voice ou Office 365 appelant Plans. Voir [Assigner de Skype pour les professionnels et les équipes Microsoft de licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Pour les activer pour Entreprise Voice, vous pouvez utiliser Windows PowerShell. Par exemple, exécutez : `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Pour en savoir plus sur Plans d'Appels Office 365, voir [Quels sont les forfaits d’appels dans Office 365 ?](/microsoftteams/what-are-calling-plans-in-office-365) et [Forfaits d'appels pour Office 365](/microsoftteams/calling-plans-for-office-365).
    
    > [!NOTE]
    > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge en tant que des Agents de file d’attente des appels. 
  
- Vous pouvez seulement attribuer les numéros de service payants et gratuits que vous avez obtenus dans le **centre d’administration de Skype Entreprise** ou transférés depuis un autre fournisseur de services vers le système téléphonique des files d’attente d'appels. Pour obtenir et utiliser les numéros de services gratuits, vous devez configurer les crédits de communication.
    
    > [!NOTE]
    > Les numéros de téléphone des utilisateurs (abonnés) ne peuvent pas être attribués à des files d'attente. Seuls les numéros de téléphone gratuits et payants peuvent être utilisés. 
  
- Lorsque vous distribuez les appels entrants à partir d’une file d’attente des appels système téléphonique, ces clients sont pris en charge pour les agents d’appel :
    
  - Client de bureau Skype Entreprise 2016 (versions 32 et 64 bits)
    
  - Client de bureau Lync 2013 (versions 32 et 64 bits)
    
  - Tous les modèles de téléphone IP pris en charge par Skype Entreprise Online. Consultez [Obtention de numéros de téléphone pour Skype Entreprise Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).
    
  - Client Mac Skype Entreprise (version 16.8.196 et ultérieures) 
    
  - Client Android Skype Entreprise (version 6.16.0.9 et ultérieures)
    
  - Client iPhone Skype Entreprise (version 6.16.0 et ultérieures)
    
  - Client Mac Skype Entreprise (version 6.16.0 et ultérieures)

  - Client Microsoft Teams Windows (versions 32 et 64 bits)

  - Client Mac Microsoft Teams

  - Application iPhone Microsoft Teams

  - Application Android Microsoft Teams
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Étape 2 : obtention ou transfert de numéros de service gratuits ou payants

Avant de pouvoir créer et configurer les files d'attente, vous devrez transférer vos numéros payants et gratuits existants. Une fois que vous obtenez les numéros de téléphone service payants et gratuits, ils s'afficheront dans **le centre d’administration de Skype entreprise** > **voix** > **numéros de téléphone**et le **type de numéro** listé sera listé en tant que **Service - numéro gratuit**. Pour obtenir vos numéros de service, voir [mise en route des numéros de téléphone de service de pour Skype entreprise et les équipes Microsoft](getting-service-phone-numbers.md) ou si vous souhaitez transférer un numéro de service existant, voir [transférer des numéros de téléphone vers Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).
  
> [!NOTE]
> Si vous êtes en dehors des États-Unis, vous ne pouvez pas utiliser le Skype entreprise centre d’administration pour obtenir les numéros de service. Accédez à [Gérer les numéros de téléphone pour votre organisation](/microsoftteams/manage-phone-numbers-for-your-organization) à la place pour voir comment le faire à partir de l’extérieur des États-Unis.
  
## <a name="step-3---create-a-new-call-queue"></a>Étape 3 : création d'une file d'attente d'appels

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**

Dans le **Centre d'administration de Skype Entreprise**, cliquez sur **Routage des appels** > **Files d'attente d'appels**, puis cliquez sur **Ajouter nouveau**:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>Définissez le nom d'affichage de la file d'attente, un numéro de téléphone et un domaine (le cas échéant).

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![Numéro 1](../images/sfbcallout1.png)<br/>
**Nom** Entrez un nom d'affichage descriptif pour la file d'attente d'appels. Le nom est obligatoire et peut contenir jusqu'à 64 caractères, espaces compris.<br/> Ce nom sera affiché dans la notification de l'appel entrant.
***
![Numéro 2](../images/sfbcallout2.png)<br/>**Numéro de téléphone** Sélectionnez un numéro de service gratuit ou payant pour la file d'attente d'appels. Cette étape est facultative. <br/> Si aucun numéro n'est répertorié, vous devrez obtenir des numéros de service avant de créer cette file d'attente. Pour obtenir vos numéros de service, voir les [numéros de téléphone de service de mise en route pour Skype pour les professionnels et les équipes Microsoft](getting-service-phone-numbers.md)
***
![Numéro 3](../images/sfbcallout3.png)<br/>**Domaine** S'il est disponible, sélectionnez le domaine Office 365 que vous souhaitez utiliser. Ce champ sera uniquement disponible si vous disposez de plusieurs domaine utilisés avec Office 365. Si c'est le cas, vous devez choisir le nom de domaine dans la liste. <br/> Par exemple, le domaine peut se présenter comme suit :  _contoso.com or redmond.contoso.com_
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Définir le message d'accueil et la musique lue pendant la mise en attente

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>Le **message d'accueil** est facultatif. Il s’agit du message d’accueil qui est diffusé aux utilisateurs d’appel dans le nombre de file d’attente d’appel. <br/> Vous pouvez télécharger un fichier audio (format .wav, .mp3 ou .wma).
***
![Numéro 2](../images/sfbcallout2.png)<br/>**Musicale** Vous pouvez utiliser la musique par défaut en attente fournie avec la file d’attente de l’appel, ou vous pouvez télécharger un fichier audio .wav ou .wma mp3 formats à utiliser en tant que votre musique personnalisée en attente. 
   

### <a name="select-the-call-distribution-method"></a>Sélectionner la méthode de distribution d’appel

![Indique les options de méthodes de distribution d'appel](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>**Méthode de distribution d'appel** Vous pouvez choisir **A la chaîne** ou **En série** pour la votre méthode de distribution d'appel de votre file d’attente. Toutes les files d’attente d'appels nouvelles et existantes seront réglés par défaut sur le routage à la chaîne. Pour utiliser le routage en série, vous devez choisir explicitement l’option routage **en série** dans l’IU et les applets de commande. <br/><br/> Lorsque le routage en série est sélectionné et que la file d’attente d’appel est enregistrée, les appels depuis la file d’attente sonneront chez les agents un à un, à partir du début de la liste d’agents. Si un agent manque ou ne décroche pas un appel, l’appel sonnera chez l’agent suivant dans la liste et tentera tous les agents un à un jusqu'à ce qu’il soit décroché ou que le délai d’attente s'épuise.   

> [!NOTE]
> Ce type de routage passera les agents qui sont **déconnectés**, qui ont réglé leur présence sur **Ne pas déranger** ou ont choisi d'être **exclus** de la réception d'appels depuis cette file d’attente. 
   
### <a name="select-an-agent-opt-out-option"></a>Sélectionner une option d'exclusion d'agent

![Montre la case à cocher d'exclusion de l’agent](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>**Option d'exclusion d'agent** Vous pouvez choisir d’autoriser les téléopérateurs à refuser de prendre des appels à partir d’une file d’attente spécifique en sélectionnant **Option d'exclusion d'agent**.  <br/> L’activation de cette option permet à tous les agents dans cette file d’attente de commencer à ou d'arrêter de recevoir à volonté des appels à partir de cette file d’attente d’appel. Vous pouvez révoquer le privilège d’exclusion d'agent à tout moment en désactivant la case à cocher, grâce à laquelle les agents sont automatiquement accrédités à nouveau pour cette file d’attente (paramètre par défaut pour tous les agents).  <br/><br/> Pour accéder à l’option d'exclusion, les agents peuvent procéder comme suit :
 1. Ouvrir **Options** dans leur client Skype Entreprise de bureau. 
 2. Sous l’onglet **Renvoi d’appel**, cliquer sur le lien **Modifier les paramètres en ligne**.
 3. Dans la page de paramètres utilisateur, cliquer sur **Files d’attente d'appels**, puis désactiver les cases à cocher des files d’attente desquelles ils souhaitent être exclus.
 
    > [!NOTE] 
    > Les agents utilisant les clients Mac, mobile, ou Lync 2013, ou les utilisateurs Hybrid Voice qui sont hébergés localement à l’aide du serveur Skype Entreprise 2015, peuvent aller à [https://aka.ms/cqsettings](https://aka.ms/cqsettings) pour accéder à l’option d'exclusion.
   
### <a name="add-call-agents-to-a-call-queue"></a>Ajouter des téléopérateurs à une file d'attente d'appels

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/><br/>Les téléopérateurs (50 maximum) peuvent être :
*    Un utilisateur en ligne avec une licence de **Système téléphonique** et enregistré pour Enterprise Voice ou avec un forfait d'appel. <br/><br/> **Remarque :**  Pour rediriger les appels vers des personnes dans votre organisation en ligne, ils doivent disposer d’une licence de **Système téléphonique** et être activés pour Enterprise Voice ou un Plan de l’appel. Voir [Assigner de Skype pour les professionnels et les équipes Microsoft de licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Pour les activer pour Entreprise Voice, vous pouvez utiliser Windows PowerShell. Par exemple, exécutez : `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
*    Les utilisateurs en ligne avec une licence de **Système téléphonique** et un forfait d’appels qui sont ajoutés à un groupe Office 365, une liste de distribution avec messagerie activée, ou un groupe de sécurité. Jusqu'à 30 minutes peuvent être nécessaires pour qu'un nouvel agent ajouté à une liste de distribution ou à un groupe de sécurité commence à recevoir des appels depuis une file d'attente. Un groupe de sécurité ou de la liste de distribution nouvellement créé peut prendre jusqu'à 48 heures soit disponible pour être utilisé avec les files d’attente de l’appel. Les groupes Office 365 nouvellement créés sont presqu'immédiatement disponibles. <br/> 

    > [!NOTE] 
    > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge.           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>Définir la taille maximale de la file d'attente et la durée maximale d'attente

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/><br/>**Nombre d'appels maximal dans la file d'attente** Utilisez cette valeur pour définir le nombre d'appels maximal qu'il peut y avoir simultanément dans la file d'attente. La valeur par défaut est de 50, mais elle peut compris entre 0 et 200. Lorsque cette limite est atteinte, l’appel sera traité de façon que vous avez défini le paramètre **lorsque le nombre maximal d’appels est atteint** ci-dessous.
***
![Numéro 2](../images/sfbcallout2.png)<br/><br/>**Lorsque le nombre maximal d’appels est atteint.** Lorsque la file d’attente d’appels atteint sa taille maximale (définie à l’aide de la valeur **maximale des appels dans la file d’attente** ), vous pouvez choisir que se passe-t-il au nouvel appel entrant.
*    **Déconnexion avec signal Occupé** L'appel sera déconnecté.
*    **Transférer cet appel** Lorsque vous choisissez cette option, vous devez ces options :
     *    **Personne de votre société** Un utilisateur en ligne avec une licence de **Système téléphonique** et être activé pour Enterprise Voice ou possèdent un Plan de l’appel. Vous pouvez configurer de telle manière que l'appelant soit renvoyé vers la messagerie vocale. Pour ce faire, sélectionnez une **personne de votre société** et définissez cette personne pour que leurs appels transférés directement vers la messagerie vocale. <br/> <br/>Pour plus d’informations sur les licences requises pour la messagerie vocale, voir [Configurer le système téléphonique de la messagerie vocale](/microsoftteams/set-up-phone-system-voicemail). 
     
        > [!Note]
        > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge.<br/>
     
     *    **File d’attente des appels** Vous devez avoir déjà créé une autre file d’attente d’appel, mais une fois que vous le faites, vous pouvez sélectionner cette file d’attente de l’appel.
     *    **Standard automatique** Vous devez avoir déjà créé un standard automatique, mais une fois que vous le faites, vous pouvez sélectionner ce standard automatique. Consultez la rubrique [configurer un standard automatique de système téléphonique](set-up-a-phone-system-auto-attendant.md).
***
![Numéro 3](../images/sfbcallout3.png)<br/><br/>**Durée d'attente d'un appel dans la file d'attente** Vous pouvez également décider de la durée maximale pendant laquelle un appel peut être mis en attente avant d'expirer ou d'être redirigé. La destination de redirection est basée sur la définition du paramètre **Lorsqu'un appel expire**. Le délai peut être défini entre 0 et 45 minutes. <br/><br/> La valeur du délai d’attente peut être réglée en secondes, par intervalles de 15 secondes. Cela vous permet de manipuler le flux des appels avec une granularité plus fine. Par exemple, vous pouvez spécifier que tous les appels qui restent sans réponse chez un agent pendant 30 secondes soient transférés vers un standard automatique d'annuaire de recherche. 

***
![Numéro 4](../images/sfbcallout4.png)<br/><br/>**Lorsqu'un appel expire** Lorsque l'appel atteint la limite définie par le paramètre **Durée d'attente d'un appel dans la file d'attente**, vous pouvez choisir le traitement ultérieur de l'appel en question :
*    **Déconnecter** L'appel sera déconnecté.
*    **Transférer cet appel** Lorsque vous choisissez cette option, vous devez ces options :
     *    **Personne de votre société** Un utilisateur en ligne avec une licence de **Système téléphonique** et être activé pour Enterprise Voice ou possèdent des Plans de l’appel. Vous pouvez configurer de telle manière que l'appelant soit renvoyé vers la messagerie vocale. Pour ce faire, sélectionnez une **personne de votre société** et définissez cette personne pour que leurs appels transférés directement vers la messagerie vocale. </br><br/>  Pour plus d’informations sur les licences requises pour la messagerie vocale, voir [Configurer le système téléphonique de la messagerie vocale](/microsoftteams/set-up-phone-system-voicemail). 

        > [!Note]
        > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge.<br/>

     *    **File d’attente des appels** Vous devez avoir déjà créé une autre file d’attente d’appel, mais une fois que vous le faites, vous pouvez sélectionner cette file d’attente de l’appel.
     *    **Standard automatique** Vous devez avoir déjà créé un standard automatique, mais une fois que vous le faites, vous pouvez sélectionner ce standard automatique. Consultez la rubrique [configurer un standard automatique de système téléphonique](set-up-a-phone-system-auto-attendant.md).
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Modifier l'ID de l’appelant de l’utilisateur pour le transformer en numéro de téléphone de la file d’attente

Vous pouvez protéger l’identité d’un utilisateur en créant une stratégie utilisant la commande d'applet **New-CallingLineIdentity**, plutôt qu'en modifiant son ID d’appelant pour les appels sortants vers une file d’attente d’appel.
  
Pour ce faire, exécutez :
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Ensuite, appliquez la stratégie à l’utilisateur à l’aide de l’applet de commande **Grant-CallingLineIdentity** . Pour ce faire, exécutez :
  
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

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
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

  
 
