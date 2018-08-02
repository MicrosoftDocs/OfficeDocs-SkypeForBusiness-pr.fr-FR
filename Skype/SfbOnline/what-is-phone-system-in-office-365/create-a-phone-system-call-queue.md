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
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 'Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options. '
ms.openlocfilehash: 9b86bec84846dff36e509488eb34f0415fe8cd95
ms.sourcegitcommit: 247747ec19c0f5c1d45fea7e5ac5318e4d5127ea
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2018
ms.locfileid: "21708349"
---
# <a name="create-a-phone-system-call-queue"></a>Créer une file d’attente de système téléphonique

Appel de système téléphonique files d’attente contiennent le message d’accueil qui est utilisés lorsqu’une personne appelle un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la capacité de recherche pour l’agent disponible appel suivant gérer l’appel pendant les personnes qui appel Écoutez une musique d’attente. Vous pouvez créer une seule ligne ou plusieurs files d’attente d’appel pour votre organisation.
  
Files d’attente des appels téléphoniques système peuvent fournir :
  
- Un message d'accueil pour l'organisation
    
- Une attente musicale
    
- Redirection d’appels pour appeler les agents dans les groupes de sécurité et les listes de distribution à extension messagerie.
    
- Définir des paramètres pour la taille maximale de file d’attente appel, délai d’expiration et options de gestion des appels.
    
Lorsqu’une personne appelle un numéro de téléphone qui est défini d’une file d’attente de l’appel, ils entendra un message d’accueil premier (si une est configuré), puis ils sera placée dans la file d’attente et attendre le prochain agent appel disponible. L'appelant entendra une musique pendant la mise en attente et les téléopérateurs répondront dans l'ordre d'arrivée des appels ( *premier entré, premier sorti*  ).
  
Tous les appels en attente dans la file d’attente seront distribués à l’aide d’un mode de routage standard ou le mode de routage en série :
  
- Avec le routage standard, le premier appel dans la file d’attente sonnera tous les agents en même temps.
    
- Avec le routage en série, le premier appel dans la file d’attente sonnera tous les agents appel un par un.
    
    > [!NOTE]
    > Appel des agents qui sont **en mode hors connexion**, ont défini leur présence **ne pas** déranger ou qui ont opté en dehors de la file d’attente de l’appel ne sera pas appelés.
  
- Une seule notification d'appel entrant (pour l'appel en tête de file) sera envoyée aux téléopérateurs à la fois.
    
- Lorsqu'un téléopérateur accepte l'appel, le prochain appel entrant dans la file d'attente sonnera pour les autres téléopérateurs.
    
## <a name="step-1---getting-started"></a>Étape 1 : prise en main

Avant de commencer à utiliser les files d'attente d'appels, il est impératif de noter les points suivants :
  
- Votre organisation doit avoir (au minimum), une licence entreprise E3 plus **Système téléphonique** ou une licence Enterprise E5. Le nombre de licences utilisateur **Système téléphonique** qui sont assignés affecte le nombre de numéros de service qui sont disponibles pour être utilisés pour les files d’attente de l’appel. Le nombre de files d’attente de l’appel que peut avoir est varie selon le nombre de licences **Système téléphonique** et de **Conférence** qui sont assignés au sein de votre organisation. Pour en savoir plus sur les licences, accédez [ici](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
    > Pour rediriger les appels vers des personnes dans votre organisation en ligne, ils doivent disposer d’une licence de **Système téléphonique** et être activés pour Enterprise Voice ou Office 365 appelant Plans. Voir [Assigner de Skype pour les professionnels et les équipes Microsoft de licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Pour les activer pour Entreprise Voice, vous pouvez utiliser Windows PowerShell. Par exemple, exécutez : `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Pour en savoir plus sur Office 365 appelant Plans, voir [Quels sont les Plans de l’appel dans Office 365 ?](../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md) et [Appel des Plans pour Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md).
    
    > [!NOTE]
    > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge en tant que des Agents de file d’attente des appels. 
  
- Vous pouvez uniquement attribuer payants et les numéros de téléphone gratuit service que vous avez obtenu dans le **Skype entreprise centre d’administration** ou transférés à partir d’un autre fournisseur de services aux files d’attente des appels système téléphonique. Pour obtenir et utiliser des numéros gratuits service, vous devez configurer les crédits de Communications.
    
    > [!NOTE]
    > Les numéros de téléphone des utilisateurs (abonnés) ne peuvent pas être attribués à des files d'attente. Seuls les numéros de téléphone gratuits et payants peuvent être utilisés. 
  
- Lorsque vous distribuez les appels entrants à partir d’une file d’attente des appels système téléphonique, ces clients sont pris en charge pour les agents d’appel :
    
  - Client de bureau Skype Entreprise 2016 (versions 32 et 64 bits)
    
  - Client de bureau Lync 2013 (versions 32 et 64 bits)
    
  - Tous les modèles de téléphone IP pris en charge par Skype Entreprise Online. Consultez [Obtention de numéros de téléphone pour Skype Entreprise Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).
    
  - Mac Skype pour Client d’entreprise (version 16.8.196 et versions ultérieures) 
    
  - Android Skype pour Client d’entreprise (version 6.16.0.9 et versions ultérieures)
    
  - iPhone Skype pour Client d’entreprise (version 6.16.0 et versions ultérieures)
    
  - iPad Skype pour Client d’entreprise (version 6.16.0 et versions ultérieures)

  - Client Microsoft équipes Windows (versions 32 et 64 bits)

  - Client Microsoft équipes Mac

  - Microsoft Teams iPhone application

  - Les équipes Microsoft pour Android
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Étape 2 : obtention ou transfert de numéros de service gratuits ou payants

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. Une fois que vous obtenez les numéros de téléphone gratuit service payant, elles seront afficheront dans **Skype pour le centre d’administration Business** > **vocale** > **numéros de téléphone**et la volonté de **type numérique** présent figurer en tant que **Service - numéro gratuit **. Pour obtenir vos numéros de service, voir les [numéros de téléphone de service de mise en route pour Skype pour les professionnels et les équipes Microsoft](getting-service-phone-numbers.md) ou si vous souhaitez transférer et le numéro de service existant, voir [transférer des numéros de téléphone vers Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Si vous êtes en dehors des États-Unis, vous ne pouvez pas utiliser le Skype entreprise centre d’administration pour obtenir les numéros de service. Accédez à [Gérer les numéros de téléphone pour votre organisation](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) à la place pour voir comment le faire à partir de l’extérieur des États-Unis.
  
## <a name="step-3---create-a-new-call-queue"></a>Étape 3 : création d'une file d'attente d'appels

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**

Dans le **Centre d'administration de Skype Entreprise**, cliquez sur **Routage des appels** > **Files d'attente d'appels**, puis cliquez sur **Ajouter nouveau**:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>Définissez le nom d'affichage de la file d'attente, un numéro de téléphone et un domaine (le cas échéant).

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![N ° 1](../images/sfbcallout1.png)<br/>
**Nom** Entrez un nom d'affichage descriptif pour la file d'attente d'appels. Le nom est obligatoire et peut contenir jusqu'à 64 caractères, espaces compris.<br/> Ce nom sera affiché dans la notification de l'appel entrant.
***
![N ° 2](../images/sfbcallout2.png)<br/>**Numéro de téléphone** Sélectionnez un numéro de service gratuit ou payant pour la file d'attente d'appels. Cette étape est facultative. <br/> Si aucun numéro n'est répertorié, vous devrez obtenir des numéros de service avant de créer cette file d'attente. Pour obtenir vos numéros de service, voir les [numéros de téléphone de service de mise en route pour Skype pour les professionnels et les équipes Microsoft](getting-service-phone-numbers.md)
***
![N ° 3](../images/sfbcallout3.png)<br/>**Domaine** S'il est disponible, sélectionnez le domaine Office 365 que vous souhaitez utiliser. Ce champ sera uniquement disponible si vous disposez de plusieurs domaine utilisés avec Office 365. Si c'est le cas, vous devez choisir le nom de domaine dans la liste.<br/> Par exemple, le domaine peut se présenter comme suit :  _contoso.com or redmond.contoso.com_
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Définir le message d'accueil et la musique lue pendant la mise en attente

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![N ° 1](../images/sfbcallout1.png)<br/>Le **message d'accueil** est facultatif. Il s’agit du message d’accueil qui est diffusé aux utilisateurs d’appel dans le nombre de file d’attente d’appel. <br/> Vous pouvez télécharger un fichier audio (format .wav, .mp3 ou .wma).
***
![N ° 2](../images/sfbcallout2.png)<br/>**Musicale** Vous pouvez utiliser la musique par défaut en attente fournie avec la file d’attente de l’appel, ou vous pouvez télécharger un fichier audio .wav ou .wma mp3 formats à utiliser en tant que votre musique personnalisée en attente. 
   

### <a name="select-the-call-distribution-method"></a>Sélectionnez la méthode de distribution d’appel

![Indique l’appel de méthode options de distribution](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![N ° 1](../images/sfbcallout1.png)<br/>**Appelez la méthode de distribution** Vous pouvez choisir **standard** ou **série** de votre méthode de distribution appel file d’attente. Toutes les files d’attente de nouveaux et existants appel aura attendant routage sélectionnée par défaut. Pour utiliser le routage en série, vous devez choisir explicitement l’option routage **en série** dans l’interface utilisateur et les applets de commande. <br/><br/> Lorsque ce type de routage est sélectionnée et que la file d’attente de l’appel est enregistré, les appels à partir de la file d’attente sonnera vos agents un par un, à partir du début de la liste d’agents. Si un agent fait disparaître ou ne récupère pas d’un appel, l’appel sonnera l’agent suivant dans la liste et essayez de tous les agents un par un jusqu'à ce qu’elle est choisie ou délai d’attente dans la file d’attente.   

> [!NOTE]
> Ce type de routage ignore les agents qui sont **en mode hors connexion**, qui ont la valeur leur présence **ne pas déranger**ou ont **choisi** de recevoir des appels à partir de cette file d’attente. 
   
### <a name="select-an-agent-opt-out-option"></a>Sélectionnez un agent exclure option

![Case à cocher indique que l’agent d’abonnement](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![N ° 1](../images/sfbcallout1.png)<br/>**Agent exclure option** Vous pouvez choisir d’autoriser les agents de file d’attente d’appel refuser de prendre des appels à partir d’une file d’attente spécifique en sélectionnant **l’Option Refuser l’Agent**.  <br/> L’activation de cette option permet de seront tous les agents de cette file d’attente pour démarrer ou arrêter de recevoir des appels à partir de cette file d’attente de l’appel à. Vous pouvez révoquer le privilège d’annulations agent à tout moment en désactivant la case à cocher, à l’origine des agents sont automatiquement accrédité pour cette file d’attente à nouveau (paramètre par défaut pour tous les agents).  <br/><br/> Pour accéder à l’option exclure, les agents peuvent procédez comme suit :
 1. Ouvrez **les Options** dans leur bureau Skype pour client d’entreprise. 
 2. Sous l’onglet **Transfert d’appel** , cliquez sur le lien **Modifier les paramètres en ligne** .
 3. Dans la page de paramètres utilisateur, cliquez sur **Appeler les files d’attente**, puis désactivez les cases à cocher des files d’attente pour lesquelles ils souhaitent sortir.
 
    > [!NOTE] 
    > Agents à l’aide de Mac, mobile, ou clients Lync 2013 ou les utilisateurs de voix hybride qui sont hébergés sur site à l’aide de Skype pour serveur Business 2015, peut atteindre [https://aka.ms/cqsettings](https://aka.ms/cqsettings) pour accéder à l’abonnement option.
   
### <a name="add-call-agents-to-a-call-queue"></a>Ajouter des téléopérateurs à une file d'attente d'appels

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![N ° 1](../images/sfbcallout1.png)<br/><br/>Agents d’appel (50 maximum) peuvent être :
*    Un utilisateur en ligne avec une licence de **Système téléphonique** et activé pour Enterprise Voice ou avec un Plan de l’appel. <br/><br/> **Remarque :**  Pour rediriger les appels vers des personnes dans votre organisation en ligne, ils doivent disposer d’une licence de **Système téléphonique** et être activés pour Enterprise Voice ou un Plan de l’appel. Voir [Assigner de Skype pour les professionnels et les équipes Microsoft de licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Pour les activer pour Entreprise Voice, vous pouvez utiliser Windows PowerShell. Par exemple, exécutez : `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
*    Utilisateurs en ligne avec une licence de **Système téléphonique** et un Plan d’appel qui sont ajoutés à un groupe d’Office 365, une liste de Distribution à extension messagerie ou un groupe de sécurité. Jusqu'à 30 minutes peuvent être nécessaires pour qu'un nouvel agent ajouté à une liste de distribution ou à un groupe de sécurité commence à recevoir des appels depuis une file d'attente. Un groupe de sécurité ou de la liste de distribution nouvellement créé peut prendre jusqu'à 48 heures soit disponible pour être utilisé avec les files d’attente de l’appel. Nouvellement créé Office 365 groupes sont presque immédiatement disponibles. <br/> 

    > [!NOTE] 
    > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge.           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>Définir la taille maximale de la file d'attente et la durée maximale d'attente

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![N ° 1](../images/sfbcallout1.png)<br/><br/>**Nombre d'appels maximal dans la file d'attente** Utilisez cette valeur pour définir le nombre d'appels maximal qu'il peut y avoir simultanément dans la file d'attente. La valeur par défaut est de 50, mais elle peut compris entre 0 et 200. Lorsque cette limite est atteinte, l’appel sera traité de façon que vous avez défini le paramètre **lorsque le nombre maximal d’appels est atteint** ci-dessous.
***
![N ° 2](../images/sfbcallout2.png)<br/><br/>**Lorsque le nombre maximal d’appels est atteint.** Lorsque la file d’attente d’appels atteint sa taille maximale (définie à l’aide de la valeur **maximale des appels dans la file d’attente** ), vous pouvez choisir que se passe-t-il au nouvel appel entrant.
*    **Déconnexion avec signal Occupé** L'appel sera déconnecté.
*    **Transférer cet appel** Lorsque vous choisissez cette option, vous devez ces options :
     *    **Personne de votre société** Un utilisateur en ligne avec une licence de **Système téléphonique** et être activé pour Enterprise Voice ou possèdent un Plan de l’appel. Vous pouvez configurer de telle manière que l'appelant soit renvoyé vers la messagerie vocale. Pour ce faire, sélectionnez une **personne de votre société** et définissez cette personne pour que leurs appels transférés directement vers la messagerie vocale. <br/> <br/>Pour plus d’informations sur les licences requises pour la messagerie vocale, voir [configurer le système téléphonique de la messagerie vocale](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md). 
     
        > [!Note]
        > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge.<br/>
     
     *    **File d’attente des appels** Vous devez avoir déjà créé une autre file d’attente d’appel, mais une fois que vous le faites, vous pouvez sélectionner cette file d’attente de l’appel.
     *    **Standard automatique** Vous devez avoir déjà créé un standard automatique, mais une fois que vous le faites, vous pouvez sélectionner ce standard automatique. Consultez la rubrique [configurer un standard automatique de système téléphonique](set-up-a-phone-system-auto-attendant.md).
***
![N ° 3](../images/sfbcallout3.png)<br/><br/>**Durée d'attente d'un appel dans la file d'attente** Vous pouvez également décider de la durée maximale pendant laquelle un appel peut être mis en attente avant d'expirer ou d'être redirigé. La destination de redirection est basée sur la définition du paramètre **Lorsqu'un appel expire**. Le délai peut être défini entre 0 et 45 minutes.  <br/><br/> Peut avoir la valeur du délai d’attente en secondes, toutes les 15 secondes. Cela vous permet de manipuler le flux des appels avec une plus fine granularité. Par exemple, vous pouvez spécifier que tous les appels qui sont sans réponse dans les 30 secondes par un agent d’accéder à un standard automatique de recherche de répertoire. 

***
![N ° 4](../images/sfbcallout4.png)<br/><br/>**Lorsqu'un appel expire** Lorsque l'appel atteint la limite définie par le paramètre **Durée d'attente d'un appel dans la file d'attente**, vous pouvez choisir le traitement ultérieur de l'appel en question :
*    **Déconnecter** L'appel sera déconnecté.
*    **Transférer cet appel** Lorsque vous choisissez cette option, vous devez ces options :
     *    **Personne de votre société** Un utilisateur en ligne avec une licence de **Système téléphonique** et être activé pour Enterprise Voice ou possèdent des Plans de l’appel. Vous pouvez configurer de telle manière que l'appelant soit renvoyé vers la messagerie vocale. Pour ce faire, sélectionnez une **personne de votre société** et définissez cette personne pour que leurs appels transférés directement vers la messagerie vocale. </br><br/>  Pour plus d’informations sur les licences requises pour la messagerie vocale, voir [configurer le système téléphonique de la messagerie vocale](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md). 

        > [!Note]
        > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge.<br/>

     *    **File d’attente des appels** Vous devez avoir déjà créé une autre file d’attente d’appel, mais une fois que vous le faites, vous pouvez sélectionner cette file d’attente de l’appel.
     *    **Standard automatique** Vous devez avoir déjà créé un standard automatique, mais une fois que vous le faites, vous pouvez sélectionner ce standard automatique. Consultez la rubrique [configurer un standard automatique de système téléphonique](set-up-a-phone-system-auto-attendant.md).
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Modification des ID de l’appelant de l’utilisateur pour qu’il soit le numéro de téléphone d’un appel de la file d’attente

Vous pouvez protéger l’identité d’un utilisateur en modifiant son ID d’appelant pour les appels sortants vers une file d’attente de l’appel au lieu de cela en créant une stratégie à l’aide de l’applet de commande **New-CallingLineIdentity** .
  
Pour ce faire, exécutez :
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Ensuite, appliquer la stratégie à l’utilisateur à l’aide de l’applet de commande **Grant-CallingLineIdentity** . Pour ce faire, exécutez :
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Vous pouvez obtenir plus d’informations sur la façon d’apporter des modifications aux paramètres d’ID de l’appelant dans votre organisation [ici](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="want-to-know-more"></a>Vous souhaitez en savoir plus ?

Vous pouvez également utiliser PowerShell Windows pour créer et configurer des files d'attente.
  
### <a name="call-queue-cmdlets"></a>Applets de commande de file d'attente d'appels

Voici les applets de commande requis pour gérer une file d'attente d'appels.
  
- [Nouvelle CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [Set-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [Get-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [Remove-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### <a name="more-about-windows-powershell"></a>Informations supplémentaires sur PowerShell Windows

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Rubriques connexes
[Voici les avantages du système téléphonique dans Office 365](here-s-what-you-get-with-phone-system.md)

[Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams](getting-service-phone-numbers.md)

[Disponibilité des offres d'appels et d'audioconférence selon les régions et les pays](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

  
 
