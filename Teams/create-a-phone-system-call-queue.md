---
title: Créer une file d’attente appel système téléphonique
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options.
ms.openlocfilehash: 3ac506f62f7b6dad35b9b1ec04fe2ffe2d612061
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/11/2019
ms.locfileid: "30543046"
---
# <a name="create-a-phone-system-call-queue"></a>Créer une file d’attente appel système téléphonique

Appel de système téléphonique files d’attente contiennent le message d’accueil qui est utilisés lorsqu’une personne appelle un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la capacité de recherche pour l’agent disponible appel suivant gérer l’appel pendant les personnes qui appel Écoutez une musique d’attente. Vous pouvez créer une seule ligne ou plusieurs files d’attente d’appel pour votre organisation.
  
Les files d’attente des systèmes téléphoniques peuvent fournir :
  
- Un message d'accueil pour l'organisation
- Une attente musicale
- Redirection d’appels pour appeler les agents dans les groupes de sécurité et les listes de distribution à extension messagerie.
- Définir des paramètres pour la taille maximale de file d’attente appel, délai d’expiration et options de gestion des appels.

Lorsqu’une personne appelle un numéro de téléphone qui est associé à une file d’attente des appels par le biais d’un [compte de ressource](manage-resource-accounts.md), elles seront entendre un message d’accueil premier (si une est configuré), puis ils sera placée dans la file d’attente et attendre le prochain agent appel disponible. La personne qui entendront musique pendant qu’ils sont mis en attente en attente et les appels seront proposés aux agents appel par ordre *First In, First Out* (FIFO).
  
Tous les appels en attente dans la file d’attente seront distribués à l’aide d’un mode de routage standard ou le mode de routage en série :
  
- Avec le routage standard, le premier appel dans la file d’attente sonnera tous les agents en même temps.
- Avec le routage en série, le premier appel dans la file d’attente sonnera chez tous les téléopérateurs un à un.

    > [!NOTE]
    > Les téléopérateurs qui sont **déconnectés**, ont défini leur présence sur **Ne pas déranger,** ou ont désactivé la file d’attente ne seront pas appelés.
  
- Une seule notification d'appel entrant (pour l'appel en tête de file) sera envoyée aux téléopérateurs à la fois.
- Lorsqu'un téléopérateur accepte l'appel, le prochain appel entrant dans la file d'attente sonnera pour les autres téléopérateurs.

> [!NOTE]
> Cet article s’applique à Microsoft Teams et Skype pour Business Online.

## <a name="step-1---getting-started"></a>Étape 1 : prise en main

Avant de commencer à utiliser les files d'attente d'appels, il est impératif de noter les points suivants :
  
- Votre organisation doit avoir (au minimum), une licence entreprise E3 plus **Système téléphonique** ou une licence Enterprise E5. Le nombre de licences utilisateur **Système téléphonique** qui sont assignés affecte le nombre de numéros de service qui sont disponibles pour être utilisés pour les files d’attente de l’appel. Le nombre de files d’attente de l’appel que peut avoir est varie selon le nombre de licences **Système téléphonique** et de **Conférence** qui sont assignés au sein de votre organisation. Pour plus d’informations sur les licences, voir [Skype pour les licences d’entreprise et les équipes Microsoft module complémentaire](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

    > [!NOTE]
    > Pour rediriger les appels vers des personnes dans votre organisation en ligne, ils doivent disposer d’une licence de **Système téléphonique** et être activés pour Enterprise Voice ou Office 365 appelant Plans. Voir [Assigner de Skype pour les professionnels et les équipes Microsoft de licences](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Pour les activer pour Entreprise Voice, vous pouvez utiliser Windows PowerShell. Par exemple, exécutez : `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Pour en savoir plus sur Plans d'Appels Office 365, voir [Quels sont les forfaits d’appels dans Office 365 ?](what-are-calling-plans-in-office-365.md) et [Forfaits d'appels pour Office 365](calling-plans-for-office-365.md).

    > [!NOTE]
    > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge comme une file d’attente d’appel Agents.
  
- Vous pouvez uniquement attribuer payants et les numéros de téléphone gratuit service que vous avez obtenu dans le **Centre d’administration de Microsoft équipes** ou transférés à partir d’un autre fournisseur de services aux files d’attente des appels système téléphonique. Pour obtenir et utiliser les numéros de services gratuits, vous devez configurer les crédits de communication.

    > [!NOTE]
    > Les numéros de téléphone des utilisateurs (abonnés) ne peuvent pas être attribués à des files d'attente. Seuls les numéros de téléphone gratuits et payants peuvent être utilisés.
  
- Lorsque vous distribuez les appels entrants à partir d’une file d’attente des appels système téléphonique, ces clients sont pris en charge pour les agents d’appel :

  - Client de bureau Skype Entreprise 2016 (versions 32 et 64 bits)

  - Client de bureau Lync 2013 (versions 32 et 64 bits)

  - Tous les modèles de téléphone IP pris en charge pour Microsoft Teams. Consultez [Obtention de numéros de téléphone pour Skype Entreprise Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).

  - Client Mac Skype Entreprise (version 16.8.196 et ultérieures)

  - Client Android Skype Entreprise (version 6.16.0.9 et ultérieures)

  - Client iPhone Skype Entreprise (version 6.16.0 et ultérieures)

  - Client Mac Skype Entreprise (version 6.16.0 et ultérieures)

  - Client Microsoft Teams Windows (versions 32 et 64 bits)

  - Client Mac Microsoft Teams

  - Application iPhone Microsoft Teams

  - Application Android Microsoft Teams

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Étape 2 : obtention ou transfert de numéros de service gratuits ou payants

Avant de pouvoir créer et configurer les files d'attente, vous devrez transférer vos numéros payants et gratuits existants. Une fois que vous obtenez les numéros de téléphone gratuit service payant, ils s’affichent dans le **Centre d’administration de Microsoft équipes** > **vocale** > **numéros de téléphone**et la volonté de **type numérique** présent figurer en tant que **Service - gratuit**. Pour obtenir vos numéros de service, voir les [numéros de téléphone de mise en service](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md) , ou si vous souhaitez transférer un numéro de service existant, voir les [numéros de téléphone transfert vers Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Si vous êtes en dehors des États-Unis, vous ne pouvez pas utiliser le centre d’administration Microsoft Teams pour obtenir les numéros de service. Accédez à [Gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) à la place pour voir comment le faire à partir de l’extérieur des États-Unis.

Si vous configurez également les standards automatiques, vous devrez uniquement affecter un numéro de téléphone pour le compte du service de surveillance automatique principal de la ressource, puis d’appelants directs à votre file d’attente de l’appel. Si tel est le cas, la file d’attente d’appel vous devrez être créé avant de pouvoir créer une option dans le standard automatique de sélectionne la file d’attente de l’appel.
  
## <a name="step-3---create-a-new-call-queue"></a>Étape 3 : créer une nouvelle file d’attente d’appel

> [!IMPORTANT]
> Chaque file d’attente de l’appel doit posséder un [compte de ressource](manage-resource-accounts.md)associé. Vous devez d’abord créer le compte de ressources, puis vous pouvez l’associer à la file d’attente de l’appel.

### <a name="using-the-microsoft-teams-admin-center"></a>À l’aide du centre d’administration Microsoft Teams

Dans le **Centre d’administration de Microsoft équipes**, **voix** >  **files d’attente des appels**, puis cliquez sur **+ Nouveau**:

### <a name="set-the-call-queue-display-name-and-resource-account"></a>Définir le complet de file d’attente appel qu’un compte nom et des ressources

![Setting up a call queue.](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

![N ° 1](media/sfbcallout1.png)
**nom** Entrez un nom d’affichage de la description de la file d’attente de l’appel. Le nom est obligatoire et peut contenir jusqu'à 64 caractères, espaces compris.

 Ce nom sera affiché dans la notification de l'appel entrant.

* * *

![Numéro 2](media/sfbcallout2.png)

**Ajouter des comptes** Sélectionnez un compte de ressource. Le compte de la ressource peut être ou non associé à un numéro payant service ou le numéro de téléphone gratuit pour la file d’attente de l’appel, mais chaque file d’attente d’appel requiert un compte de ressource.

Si il n’existe pas dans la liste, vous devez obtenir les numéros de service et les affecter à un compte de ressource avant de pouvoir créer cette file d’attente de l’appel, comme décrit précédemment. Pour obtenir vos numéros de service, voir les [numéros de téléphone de mise en service](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md). Vous devez créer un compte de ressource, comme décrit dans [Gérer les comptes de ressources dans les équipes](manage-resource-accounts.md) si vous souhaitez que votre file d’attente de l’appel vers un numéro de téléphone associé.

> [!NOTE]
> Si vous souhaitez ou que vous devez lui assigner un **domaine** ferait en l’affectant au compte de ressources pour la file d’attente de l’appel.

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Définir le message d'accueil et la musique lue pendant la mise en attente

![Setting up a call queue.](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
* * *

![Numéro 1](media/sfbcallout1.png)

Le **message d'accueil** est facultatif. Il s’agit du message d’accueil qui est diffusé aux utilisateurs d’appel dans le nombre de file d’attente d’appel.

Vous pouvez télécharger un fichier audio (format .wav, .mp3 ou .wma).

![Numéro 2](media/sfbcallout2.png)

**Musicale** Vous pouvez utiliser la musique par défaut en attente fournie avec la file d’attente de l’appel, ou vous pouvez télécharger un fichier audio .wav ou .wma mp3 formats à utiliser en tant que votre musique personnalisée en attente.

* * *

### <a name="select-the-call-answering-options"></a>Sélectionnez l’options de répondeur automatique

![Indique les options de méthodes de distribution d'appel](media/5d249515-d532-4af2-90da-011404028b89.png)

![Numéro 1](media/sfbcallout1.png)

Vous pouvez sélectionner jusqu'à 200 agents appel appartenant à des listes de diffusion spécifiées ou des groupes. Agents d’appel doivent être :

- Un utilisateur en ligne avec une licence de **Système téléphonique** et enregistré pour Enterprise Voice ou avec un forfait d'appel.

  > [!NOTE]
  > Pour rediriger les appels vers des personnes dans votre organisation en ligne, ils doivent disposer d’une licence de **Système téléphonique** et être activés pour Enterprise Voice ou un Plan de l’appel. Voir [Assigner de Skype pour les professionnels et les équipes Microsoft de licences](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

 Pour les activer pour Entreprise Voice, vous pouvez utiliser Windows PowerShell. Par exemple, exécutez : `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- Les utilisateurs en ligne avec une licence de **Système téléphonique** et un forfait d’appels qui sont ajoutés à un groupe Office 365, une liste de distribution avec messagerie activée, ou un groupe de sécurité. Jusqu'à 30 minutes peuvent être nécessaires pour qu'un nouvel agent ajouté à une liste de distribution ou à un groupe de sécurité commence à recevoir des appels depuis une file d'attente. Un groupe de sécurité ou de la liste de distribution nouvellement créé peut prendre jusqu'à 48 heures soit disponible pour être utilisé avec les files d’attente de l’appel. Les groupes Office 365 nouvellement créés sont presqu'immédiatement disponibles.

  > [!NOTE]
  > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge.

![Set up call queues.](media/skype-for-business-add-agents-to-call-queue.png)

![Numéro 2](media/sfbcallout2.png)

**Méthode de routage** Vous pouvez choisir soit **Attendant**, **série**ou **tourniquet (Round Robin)** pour la méthode de distribution en file d’attente de votre appel. Toutes les files d’attente d'appels nouvelles et existantes seront réglés par défaut sur le routage à la chaîne. Lorsque le routage standard est utilisé, le premier appel dans la file d’attente tous les agents appel sonnera en même temps. Le premier agent d’appel pour identifier l’appel Obtient l’appel.

- **Surveillance du routage** entraîne le premier appel dans la file d’attente pour faire sonner tous les agents d’appel en même temps. Le premier agent d’appel pour identifier l’appel Obtient l’appel.
- **Le routage de série** entraîne les appels entrants vers la sonnerie d’appel agents un par un, à partir du début de la liste d’appels de l’agent. Si un agent manque ou ne décroche pas un appel, l’appel sonnera chez l’agent suivant dans la liste et tentera tous les agents un à un jusqu'à ce qu’il soit décroché ou que le délai d’attente s'épuise.
  > [!NOTE]
  > Ce type de routage passera les agents qui sont **déconnectés**, qui ont réglé leur présence sur **Ne pas déranger** ou ont choisi d'être **exclus** de la réception d'appels depuis cette file d’attente.
- **Round robin** répartit le routage des appels entrants afin que chaque agent appel le même nombre d’appels à partir de la file d’attente. Cela peut être très souhaitable dans un environnement de vente entrant afin de garantir l’opportunité égale entre tous les agents de l’appel.

### <a name="select-an-agent-opt-out-option"></a>Sélectionner une option d'exclusion d'agent

![Montre la case à cocher d'exclusion de l’agent](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
* * *

![Numéro 1](media/sfbcallout1.png)

**Option d'exclusion d'agent** Vous pouvez choisir d’autoriser les téléopérateurs à refuser de prendre des appels à partir d’une file d’attente spécifique en sélectionnant **Option d'exclusion d'agent**.

L’activation de cette option permet de seront tous les agents de cette file d’attente pour démarrer ou arrêter de recevoir des appels à partir de cette file d’attente de l’appel à. Vous pouvez révoquer le privilège d’exclusion d'agent à tout moment en désactivant la case à cocher, grâce à laquelle les agents sont automatiquement accrédités à nouveau pour cette file d’attente (paramètre par défaut pour tous les agents).

Pour accéder à l’option d'exclusion, les agents peuvent procéder comme suit :

 1. Ouvrir **Options** dans leur client Skype Entreprise de bureau.
 2. Sous l’onglet **Renvoi d’appel**, cliquer sur le lien **Modifier les paramètres en ligne**.
 3. Dans la page de paramètres utilisateur, cliquer sur **Files d’attente d'appels**, puis désactiver les cases à cocher des files d’attente desquelles ils souhaitent être exclus.

    > [!NOTE]
    > Les agents utilisant les clients Mac, mobile, ou Lync 2013, ou les utilisateurs Hybrid Voice qui sont hébergés localement à l’aide du serveur Skype Entreprise 2015, peuvent aller à [https://aka.ms/cqsettings](https://aka.ms/cqsettings) pour accéder à l’option d'exclusion.

![N ° 2](media/sfbcallout2.png)
**paramètre d’alerte de l’Agent**

Définit la durée d’un agent être averti d’un appel avant le numéro de série ou tourniquet (Round Robin) des méthodes de routage déplacement vers l’agent suivant.

Le paramètre par défaut est de 30 secondes, mais elle peut être définie pour 3 minutes.

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a>Définir des options de gestion de l’appel de dépassement de capacité et délai d’expiration

![Set up a call queue.](media/3f018734-16fe-458b-827d-71fc25155cde.png)
  
* * *

![Numéro 1](media/sfbcallout1.png)

**Nombre d'appels maximal dans la file d'attente** Utilisez cette valeur pour définir le nombre d'appels maximal qu'il peut y avoir simultanément dans la file d'attente. La valeur par défaut est 50, mais elle compris entre 0 et 200. Lorsque la limite est atteinte, l'appel sera traité de la manière définie par le paramètre **Lorsque la limite maximale du nombre d'appels est atteinte** ci-après.

* * *

![Numéro 2](media/sfbcallout2.png)

**Lorsque le nombre maximal d’appels est atteint.** Lorsque la file d’attente d’appels atteint sa taille maximale (définie à l’aide de la valeur **maximale des appels dans la file d’attente** ), vous pouvez choisir que se passe-t-il au nouvel appel entrant.

- **Déconnecter** L'appel sera déconnecté.
- **Rediriger vers** Lorsque vous choisissez cette option, sélectionnez une des options suivantes :

  - **Personne de votre société** Un utilisateur en ligne avec une licence de **Système téléphonique** et être activé pour Enterprise Voice ou possèdent un Plan de l’appel. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour ce faire, sélectionnez une **personne de votre société** et définissez cette personne pour que leurs appels transférés directement vers la messagerie vocale.

  Pour plus d’informations sur les licences requises pour la messagerie vocale, voir [Configurer le système téléphonique de la messagerie vocale](set-up-phone-system-voicemail.md).

    > [!Note]
    > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge.
  - **Application vocale** Sélectionnez le nom de l’une file d’attente de l’appel ou qui a déjà été créée standard automatique.

* * *

![Nombre 3](media/sfbcallout3.png)

**Délai d’attente des appels : temps d’attente maximal** Vous pouvez également choisir combien de temps un appel peut être en attente dans la file d’attente avant qu’il arrive à expiration et doit être redirigé ou déconnecté. La destination de redirection est basée sur la définition du paramètre **Lorsqu'un appel expire**. Le délai peut être défini entre 0 et 45 minutes.

La valeur du délai d’attente peut être réglée en secondes, par intervalles de 15 secondes. Cela vous permet de manipuler le flux des appels avec une granularité plus fine. Par exemple, vous pouvez spécifier que tous les appels qui sont sans réponse dans les 30 secondes par un agent d’accéder à un standard automatique de recherche dans l’annuaire.

![Numéro 4](media/sfbcallout4.png)

**Lorsque le délai d’attente expire** Lorsque l’appel atteint la limite que vous définissez le paramètre de **la durée pendant laquelle un appel peut attendre dans la file d’attente** , vous pouvez choisir que se passe-t-il à cet appel :

- **Déconnecter** L'appel sera déconnecté.
- **Cet appel de redirection** Lorsque vous choisissez cette option, vous devez ces options :
  - **Personne de votre société** Un utilisateur en ligne avec une licence de **Système téléphonique** et être activé pour Enterprise Voice ou possèdent des Plans de l’appel. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour ce faire, sélectionnez une **personne de votre société** et définissez cette personne pour que leurs appels transférés directement vers la messagerie vocale.

  Pour plus d’informations sur les licences requises pour la messagerie vocale, voir [Configurer le système téléphonique de la messagerie vocale](set-up-phone-system-voicemail.md).

    > [!Note]
    > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge.

  - **Application vocale** Sélectionnez le nom de l’une file d’attente de l’appel ou qui a déjà été créée standard automatique.

## <a name="changing-a-users-caller-id-to-be-a-call-queues-phone-number"></a>Modification des ID de l’appelant d’un utilisateur pour qu’il soit le numéro de téléphone d’un appel de la file d’attente

Vous pouvez protéger l’identité d’un utilisateur en créant une stratégie utilisant la commande d'applet **New-CallingLineIdentity**, plutôt qu'en modifiant son ID d’appelant pour les appels sortants vers une file d’attente d’appel.

Pour ce faire, exécutez :

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Ensuite, appliquez la stratégie à l’utilisateur à l’aide de l’applet de commande **Grant-CallingLineIdentity** . Pour ce faire, exécutez :
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Vous pouvez obtenir plus d’informations sur la façon d’apporter des modifications aux paramètres d’ID de l’appelant dans votre organisation dans l’article [ID d’appelant utilisation dans votre organisation](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="want-to-know-more"></a>Vous souhaitez en savoir plus ?

Vous pouvez également utiliser PowerShell Windows pour créer et configurer des files d'attente.
  
### <a name="call-queue-cmdlets"></a>Applets de commande de file d'attente d'appels

Voici les applets de commande requis pour gérer une file d'attente d'appels.
  
- [Nouvelle-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)

- [Configurer-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)

- [Obtenir-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)

- [Supprimer-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)

### <a name="more-about-windows-powershell"></a>Informations supplémentaires sur PowerShell Windows

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Office 365 et Teams Microsoft à l’aide d’un point unique d’administration qui peut simplifier votre travail quotidien, lorsque vous avez plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :

  - [Présentation de Windows PowerShell et Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell présente de nombreux avantages dans vitesse, la simplicité et la productivité sur qu’à l’aide du centre d’administration Microsoft Teams tels que lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :

  - [Gérer Office 365 avec Windows PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Rubriques connexes

[Voici les avantages du système téléphonique dans Office 365](here-s-what-you-get-with-phone-system.md)

[Obtenir des numéros de téléphone de service](/Skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[Disponibilité des forfaits d'appels et de l’audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Nouvelle CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
