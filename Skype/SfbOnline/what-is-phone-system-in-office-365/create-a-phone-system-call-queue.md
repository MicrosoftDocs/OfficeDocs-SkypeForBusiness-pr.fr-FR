---
title: Créer une file d’attente appel système téléphonique
author: Jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: phans, wasseemh
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
f1keywords: ms.teamsadmincenter.callqueues.overview
ms.custom:
- Phone System
description: 'Découvrez comment configurer le système téléphonique de files d’attente d’Office 365 (en nuage PBX) appel pour vous donner une organisation message d’accueil, une musique d’attente et rediriger les appels pour appeler les agents dans des listes de distribution et les groupes de sécurité. Vous pouvez également définir la taille maximale de file d’attente, délai d’expiration et options de gestion des appels. '
ms.openlocfilehash: c76f7e00c8c12e79c0dc333e05d4ccb0ca75266a
ms.sourcegitcommit: f9a9a7e4b7f6c821a3372f7dcb966a8a6d458752
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2019
ms.locfileid: "30952350"
---
# <a name="create-a-phone-system-call-queue"></a>Créer une file d’attente appel système téléphonique

Appel de système téléphonique files d’attente contiennent le message d’accueil qui est utilisés lorsqu’une personne appelle un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la capacité de recherche pour l’agent disponible appel suivant gérer l’appel pendant les personnes qui appel Écoutez une musique d’attente. Vous pouvez créer une seule ligne ou plusieurs files d’attente d’appel pour votre organisation.
  
Files d’attente des appels téléphoniques système peuvent fournir :
  
- Un message d’accueil d’organisation.
- Musique pendant que les utilisateurs sont en attente de suspension.
- Redirection d’appels pour appeler les agents dans les groupes de sécurité et les listes de distribution à extension messagerie.
- Définir des paramètres pour la taille maximale de file d’attente appel, délai d’expiration et options de gestion des appels.

Lorsqu’une personne appelle un numéro de téléphone qui est configuré avec une file d’attente de l’appel, elles seront entendre un message d’accueil premier (si une est configuré), puis ils sera placée dans la file d’attente et attendre le prochain agent appel disponible. La personne qui entendront musique pendant qu’ils sont en attente en attente, et vous pourrez les appels vers les agents de l’appel de la manière *First In, First Out* (FIFO).
  
Tous les appels en attente dans la file d’attente seront distribués à l’aide d’un mode de routage standard ou le mode de routage en série :
  
- Avec le routage standard, le premier appel dans la file d’attente sonnera tous les agents en même temps.
- Avec le routage en série, le premier appel dans la file d’attente sonnera tous les agents appel un par un.

    > [!NOTE]
    > Appel des agents qui sont **en mode hors connexion**, ont défini leur présence **ne pas** déranger ou qui ont opté en dehors de la file d’attente de l’appel ne sera pas appelés.
  
- Vous recevrez uniquement une notification d’appel entrant (pour l’appel à la tête de la file d’attente) à la fois vers les agents d’appel.
- Une fois un agent appel accepte l’appel, le prochain appel entrant dans la file d’attente démarre simultanée des agents d’appel.

## <a name="step-1---getting-started"></a>Étape 1 : prise en main

Pour commencer à l’aide de files d’attente d’appel, il est important de n’oubliez pas de choses :
  
- Votre organisation doit avoir (au minimum), une licence entreprise E3 plus **Système téléphonique** ou une licence Enterprise E5. Le nombre de licences utilisateur **Système téléphonique** qui sont assignés affecte le nombre de numéros de service qui sont disponibles pour être utilisés pour les files d’attente de l’appel. Le nombre de files d’attente de l’appel que peut avoir est varie selon le nombre de licences **Système téléphonique** et de **Conférence** qui sont assignés au sein de votre organisation. Pour en savoir plus sur les licences, accédez [ici](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

    > [!NOTE]
    > Pour rediriger les appels vers des personnes dans votre organisation en ligne, ils doivent disposer d’une licence de **Système téléphonique** et être activés pour Enterprise Voice ou Office 365 appelant Plans. Voir [Assigner de Skype pour les professionnels et les équipes Microsoft de licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Pour les activer pour Enterprise Voice, vous pouvez utiliser Windows PowerShell. Par exemple, exécutez :  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Pour en savoir plus sur Office 365 appelant Plans, voir le [système téléphonique et Plans de l’appel](/microsoftteams/calling-plan-landing-page) et [Appel des Plans pour Office 365](/microsoftteams/calling-plans-for-office-365).

    > [!NOTE]
    > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge en tant que des Agents de file d’attente des appels. 
  
- Vous pouvez uniquement attribuer payants et les numéros de téléphone gratuit service que vous avez obtenu dans le **Skype entreprise centre d’administration** ou transférés à partir d’un autre fournisseur de services aux files d’attente des appels système téléphonique. Pour obtenir et utiliser des numéros gratuits service, vous devez configurer les crédits de Communications.

    > [!NOTE]
    > Numéros de téléphone de l’utilisateur (abonné) ne peut pas être affectés à appeler des files d’attente - le service seulement payant ou numéros de téléphone peuvent être utilisés. 
  
- Lorsque vous distribuez les appels entrants à partir d’une file d’attente des appels système téléphonique, ces clients sont pris en charge pour les agents d’appel :

  - Skype pour le client de bureau Business 2016 (versions 32 et 64 bits)

  - Client de bureau Lync 2013 (versions 32 et 64 bits)

  - Tous les modèles de téléphone IP pris en charge pour Skype pour Business Online. Consultez [Obtention de numéros de téléphone pour Skype Entreprise Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).

  - Mac Skype pour Client d’entreprise (version 16.8.196 et versions ultérieures) 

  - Android Skype pour Client d’entreprise (version 6.16.0.9 et versions ultérieures)

  - iPhone Skype pour Client d’entreprise (version 6.16.0 et versions ultérieures)

  - iPad Skype pour Client d’entreprise (version 6.16.0 et versions ultérieures)

  - Client Microsoft équipes Windows (versions 32 et 64 bits)

  - Client Microsoft équipes Mac

  - Microsoft Teams iPhone application

  - Les équipes Microsoft pour Android

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Étape 2 : obtention ou transfert payant ou des numéros de téléphone gratuit service

Avant de pouvoir créer et configurer les files d'attente, vous devrez transférer vos numéros payants et gratuits existants. Une fois que vous obtenez les numéros de téléphone service payants et gratuits, ils s'afficheront dans **le centre d’administration de Skype entreprise** > **voix** > **numéros de téléphone**et le **type de numéro** listé sera listé en tant que **Service - numéro gratuit**. Pour obtenir vos numéros de service, voir [mise en route des numéros de téléphone de service de pour Skype entreprise et les équipes Microsoft](getting-service-phone-numbers.md) ou si vous souhaitez transférer un numéro de service existant, voir [transférer des numéros de téléphone vers Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).
  
> [!NOTE]
> Si vous êtes en dehors des États-Unis, vous ne pouvez pas utiliser le Skype entreprise centre d’administration pour obtenir les numéros de service. Accédez à [Gérer les numéros de téléphone pour votre organisation](/microsoftteams/manage-phone-numbers-for-your-organization) à la place pour voir comment le faire à partir de l’extérieur des États-Unis.
  
## <a name="step-3---create-a-new-call-queue"></a>Étape 3 : créer une nouvelle file d’attente des appels

 **À l’aide du centre d’administration Microsoft Teams**

Dans le **Centre d’administration équipes Microsoft**, cliquez sur ![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Portail hérité** >  **routage des appels** > **files d’attente des appels**, puis cliquez sur **+ Nouveau**:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>Définir le nom complet de file d’attente appel, le numéro de téléphone et le domaine (le cas échéant)

![Configuration d’une file d’attente de l’appel.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![Numéro 1](../images/sfbcallout1.png)<br/>
**Nom** Entrez un nom d’affichage de la description de la file d’attente de l’appel. Cela est nécessaire et peut contenir jusqu'à 64 caractères, espaces compris. <br/> Ce nom s’affichera dans la notification de l’appel entrant.
***
![Numéro 2](../images/sfbcallout2.png)<br/>**Numéro de téléphone** Sélectionnez un numéro payant service ou le numéro de téléphone gratuit pour la file d’attente de l’appel. Cette étape est facultative. <br/> Si il n’existe pas dans la liste, vous devez obtenir les numéros de service avant de pouvoir créer cette file d’attente de l’appel. Pour obtenir vos numéros de service, voir les [numéros de téléphone de service de mise en route pour Skype pour les professionnels et les équipes Microsoft](getting-service-phone-numbers.md)
***
![Nombre 3](../images/sfbcallout3.png)<br/>**Domaine** Si cette option est disponible, choisissez le domaine Office 365 que vous souhaitez utiliser. Il est disponible uniquement si vous avez plusieurs domaines utilisés avec Office 365. Si vous avez plusieurs, vous devez a choisi le nom de domaine dans la liste. <br/> Par exemple, vous pouvez avoir un domaine comme : _contoso.com ou redmond.contoso.com_

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Définir le message d’accueil et la musique joué suspendu

![Configuration d’une file d’attente de l’appel.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>**Message d’accueil** est facultative. Il s’agit du message d’accueil qui est diffusé aux utilisateurs d’appel dans le nombre de file d’attente d’appel. <br/> Vous pouvez télécharger un fichier audio (format .wav, .mp3 ou .wma).
***
![Numéro 2](../images/sfbcallout2.png)<br/>**Musicale** Vous pouvez utiliser la musique par défaut en attente fournie avec la file d’attente de l’appel, ou vous pouvez télécharger un fichier audio .wav ou .wma mp3 formats à utiliser en tant que votre musique personnalisée en attente.

### <a name="select-the-call-distribution-method"></a>Sélectionnez la méthode de distribution d’appel

![Indique l’appel de méthode options de distribution](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>**Appelez la méthode de distribution** Vous pouvez choisir **standard** ou **série** de votre méthode de distribution appel file d’attente. Toutes les files d’attente de nouveaux et existants appel aura attendant routage sélectionnée par défaut. Pour utiliser le routage en série, vous devez choisir explicitement l’option routage **en série** dans l’interface utilisateur et les applets de commande. <br/><br/> Lorsque ce type de routage est sélectionnée et que la file d’attente de l’appel est enregistré, les appels à partir de la file d’attente sonnera vos agents un par un, à partir du début de la liste d’agents. Si un agent fait disparaître ou ne récupère pas d’un appel, l’appel sonnera l’agent suivant dans la liste et essayez de tous les agents un par un jusqu'à ce qu’elle est choisie ou délai d’attente dans la file d’attente.   

> [!NOTE]
> Ce type de routage ignore les agents qui sont **en mode hors connexion**, qui ont la valeur leur présence **ne pas déranger**ou ont **choisi** de recevoir des appels à partir de cette file d’attente. 

### <a name="select-an-agent-opt-out-option"></a>Sélectionnez un agent exclure option

![Case à cocher indique que l’agent d’abonnement](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>**Agent exclure option** Vous pouvez choisir d’autoriser les agents de file d’attente d’appel refuser de prendre des appels à partir d’une file d’attente spécifique en sélectionnant **l’Option Refuser l’Agent**.  <br/> L’activation de cette option permet de seront tous les agents de cette file d’attente pour démarrer ou arrêter de recevoir des appels à partir de cette file d’attente de l’appel à. Vous pouvez révoquer le privilège d’annulations agent à tout moment en désactivant la case à cocher, à l’origine des agents sont automatiquement accrédité pour cette file d’attente à nouveau (paramètre par défaut pour tous les agents).  <br/><br/> Pour accéder à l’option exclure, les agents peuvent procédez comme suit :
 1. Ouvrez **les Options** dans leur bureau Skype pour client d’entreprise. 
 2. Sous l’onglet **Transfert d’appel** , cliquez sur le lien **Modifier les paramètres en ligne** .
 3. Dans la page de paramètres utilisateur, cliquez sur **Appeler les files d’attente**, puis désactivez les cases à cocher des files d’attente pour lesquelles ils souhaitent sortir.

    > [!NOTE] 
    > Agents à l’aide de Mac, mobile, ou clients Lync 2013 ou les utilisateurs de voix hybride qui sont hébergés sur site à l’aide de Skype pour serveur Business 2015, peut atteindre [https://aka.ms/cqsettings](https://aka.ms/cqsettings) pour accéder à l’abonnement option.

### <a name="add-call-agents-to-a-call-queue"></a>Ajouter des agents de l’appel à une file d’attente d’appel

![Configurer les files d’attente de l’appel.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/><br/>Agents d’appel (200 maximale) peuvent être :
* Un utilisateur en ligne avec une licence de **Système téléphonique** et activé pour Enterprise Voice ou avec un Plan de l’appel. <br/><br/> **Remarque :**  Pour rediriger les appels vers des personnes dans votre organisation en ligne, ils doivent disposer d’une licence de **Système téléphonique** et être activés pour Enterprise Voice ou un Plan de l’appel. Voir [Assigner de Skype pour les professionnels et les équipes Microsoft de licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Pour les activer pour Enterprise Voice, vous pouvez utiliser Windows PowerShell. Par exemple, exécutez :  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
* Utilisateurs en ligne avec une licence de **Système téléphonique** et un Plan d’appel qui sont ajoutés à un groupe d’Office 365, une liste de Distribution à extension messagerie ou un groupe de sécurité. Il peut prendre jusqu'à 30 minutes pour un nouvel agent ajouté pour une liste de distribution ou un groupe de sécurité pour commencer à recevoir des appels à partir d’une file d’attente de l’appel. Un groupe de sécurité ou de la liste de distribution nouvellement créé peut prendre jusqu'à 48 heures soit disponible pour être utilisé avec les files d’attente de l’appel. Nouvellement créé Office 365 groupes sont presque immédiatement disponibles. <br/> 

  > [!NOTE] 
  > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge.

### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>Définir la taille maximale de file d’attente et le délai d’attente maximal

![Configurer une file d’attente de l’appel.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/><br/>**Nombre maximal des appels dans la file d’attente** Permet de définir les appels maximales qui peuvent attendre dans la file d’attente en même temps. La valeur par défaut est de 50, mais elle peut compris entre 0 et 200. Lorsque cette limite est atteinte, l’appel sera traité de façon que vous avez défini le paramètre **lorsque le nombre maximal d’appels est atteint** ci-dessous.
***
![Numéro 2](../images/sfbcallout2.png)<br/><br/>**Lorsque le nombre maximal d’appels est atteint.** Lorsque la file d’attente d’appels atteint sa taille maximale (définie à l’aide de la valeur **maximale des appels dans la file d’attente** ), vous pouvez choisir que se passe-t-il au nouvel appel entrant.
* **Déconnexion avec un signal occupé (e)** L’appel sera déconnecté.
* **Transférer cet appel** Lorsque vous choisissez cette option, vous devez ces options :
  * **Personne de votre société** Un utilisateur en ligne avec une licence de **Système téléphonique** et être activé pour Enterprise Voice ou possèdent un Plan de l’appel. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour ce faire, sélectionnez une **personne de votre société** et définissez cette personne pour que leurs appels transférés directement vers la messagerie vocale. <br/> <br/>Pour plus d’informations sur les licences requises pour la messagerie vocale, voir [configuration de la messagerie vocale dans le nuage](/microsoftteams/set-up-phone-system-voicemail). 

    > [!Note]
    > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge.<br/>

  * **File d’attente des appels** Vous devez avoir déjà créé une autre file d’attente d’appel, mais une fois que vous le faites, vous pouvez sélectionner cette file d’attente de l’appel.
  * **Standard automatique** Vous devez avoir déjà créé un standard automatique, mais une fois que vous le faites, vous pouvez sélectionner ce standard automatique. Consultez la rubrique [configurer un standard automatique de système téléphonique](set-up-a-phone-system-auto-attendant.md).
***
![Nombre 3](../images/sfbcallout3.png)<br/><br/>**La durée pendant laquelle un appel peut attendre dans la file d’attente** Vous pouvez également choisir combien de temps un appel peut être en attente dans la file d’attente avant qu’il arrive à expiration et doit être redirigé ou déconnecté. Où elle sera redirigée est basée sur la façon dont vous définissez le paramètre **lorsqu’un appel arrive à expiration** . Vous pouvez définir une durée de 0 à 45 minutes. <br/><br/> Peut avoir la valeur du délai d’attente en secondes, toutes les 15 secondes. Cela vous permet de manipuler le flux des appels avec une plus fine granularité. Par exemple, vous pouvez spécifier que tous les appels qui sont sans réponse dans les 30 secondes par un agent d’accéder à un standard automatique de recherche de répertoire. 

***
![Numéro 4](../images/sfbcallout4.png)<br/><br/>**Lorsqu’un appel arrive à expiration** Lorsque l’appel atteint la limite que vous définissez le paramètre de **la durée pendant laquelle un appel peut attendre dans la file d’attente** , vous pouvez choisir que se passe-t-il à cet appel :
* **Se déconnecter** L’appel sera déconnecté.
* **Transférer cet appel** Lorsque vous choisissez cette option, vous devez ces options :
  * **Personne de votre société** Un utilisateur en ligne avec une licence de **Système téléphonique** et être activé pour Enterprise Voice ou possèdent des Plans de l’appel. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour ce faire, sélectionnez une **personne de votre société** et définissez cette personne pour que leurs appels transférés directement vers la messagerie vocale. </br><br/>  Pour plus d’informations sur les licences requises pour la messagerie vocale, voir [configuration de la messagerie vocale dans le nuage](/microsoftteams/set-up-phone-system-voicemail). 

    > [!Note]
    > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge.<br/>

  * **File d’attente des appels** Vous devez avoir déjà créé une autre file d’attente d’appel, mais une fois que vous le faites, vous pouvez sélectionner cette file d’attente de l’appel.
  * **Standard automatique** Vous devez avoir déjà créé un standard automatique, mais une fois que vous le faites, vous pouvez sélectionner ce standard automatique. Consultez la rubrique [configurer un standard automatique de système téléphonique](set-up-a-phone-system-auto-attendant.md).
   
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

Vous pouvez également utiliser Windows PowerShell pour créer et configurer des files d’attente de l’appel.
  
### <a name="call-queue-cmdlets"></a>Cmdlets de file d’attente

Voici les applets de commande dont vous avez besoin pour gérer une file d’attente de l’appel.
  
- [Nouvelle CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)

- [Set-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)

- [Get-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)

- [Remove-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)

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
