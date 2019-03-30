---
title: Créer une file d’attente d’appel
ms.author: jambirk
author: jambirk
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
description: Découvrez comment configurer le système téléphonique de files d’attente des appels système téléphonique pour vous donner une organisation message d’accueil, une musique d’attente et rediriger les appels pour appeler les agents dans des listes de distribution et les groupes de sécurité. Vous pouvez également définir la taille maximale de file d’attente, délai d’expiration et options de gestion des appels.
ms.openlocfilehash: a44bd5b00b47655dc950ee01f82ffd0c0a308466
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012972"
---
# <a name="create-a-phone-system-call-queue"></a>Créer une file d’attente appel système téléphonique

Appel de système téléphonique files d’attente contiennent le message d’accueil qui est utilisés lorsqu’une personne appelle un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la capacité de recherche pour l’agent disponible appel suivant gérer l’appel pendant les personnes qui appel Écoutez une musique d’attente. Vous pouvez créer une seule ligne ou plusieurs files d’attente d’appel pour votre organisation.
  
Files d’attente des appels téléphoniques système peuvent fournir :
  
- Un message d’accueil d’organisation.
- Musique pendant que les utilisateurs sont en attente de suspension.
- Redirection d’appels pour appeler les agents dans les groupes de sécurité et les listes de distribution à extension messagerie.
- Définir des paramètres pour la taille maximale de file d’attente appel, délai d’expiration et options de gestion des appels.

Lorsqu’une personne appelle un numéro de téléphone qui est associé à une file d’attente des appels par le biais d’un [compte de ressource](manage-resource-accounts.md), elles seront entendre un message d’accueil premier (si une est configuré), puis ils sera placée dans la file d’attente et attendre le prochain agent appel disponible. La personne qui entendront musique pendant qu’ils sont mis en attente en attente et les appels seront proposés aux agents appel par ordre *First In, First Out* (FIFO).
  
Tous les appels en attente dans la file d’attente seront distribués à l’aide d’une des méthodes suivantes :
  
- Avec le routage standard, le premier appel dans la file d’attente sonnera tous les agents en même temps.
- Avec le routage en série, le premier appel dans la file d’attente sonnera tous les agents appel un par un.
- Avec tourniquet, le routage des appels entrants est équilibré afin que chaque agent appel le même nombre d’appels à partir de la file d’attente.

    > [!NOTE]
    > Appel des agents qui sont **en mode hors connexion**, ont défini leur présence **ne pas** déranger ou qui ont opté en dehors de la file d’attente de l’appel ne sera pas appelés.
  
- Vous recevrez uniquement une notification d’appel entrant (pour l’appel à la tête de la file d’attente) à la fois vers les agents d’appel.
- Une fois un agent appel accepte l’appel, le prochain appel entrant dans la file d’attente démarre simultanée des agents d’appel.

> [!NOTE]
> Cet article s’applique à Microsoft Teams et Skype pour Business Online.

## <a name="step-1---get-started"></a>Étape 1 : mise en route

Pour commencer à l’aide de files d’attente d’appel, il est important de n’oubliez pas de choses :
  
- Un standard automatique est nécessaire d’avoir un compte de ressource. Pour plus d’informations sur les comptes de ressources, voir [Gérer les comptes de ressources dans les équipes](manage-resource-accounts.md) .
- Si vous souhaitez affecter un numéro de routage Direct, vous devez acquérir et affecter les licences suivantes aux comptes ressource \(Office 365 entreprise E1, E3 ou E5, avec le module complémentaire système téléphonique\).
- Si vous affectez un numéro de service Microsoft au lieu de cela, vous devez acquérir et affecter les licences suivantes à votre compte de ressource \(Office 365 entreprise E1, E3 ou E5, avec le module complémentaire système téléphonique et un Plan d’appel de\).

> [!NOTE] 
> Microsoft fonctionne sur un modèle de licence approprié pour les applications telles que les standards automatiques de nuage et les files d’attente des appels, maintenant vous devez utiliser le modèle de gestion des licences utilisateur pour.

> [!NOTE]
> Pour rediriger les appels vers des personnes dans votre organisation en ligne, ils doivent disposer d’une licence de **Système téléphonique** et être activés pour Enterprise Voice ou Office 365 appelant Plans. Voir [Assigner de Skype pour les licences d’entreprise](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) ou [licences attribuer les équipes Microsoft](assign-teams-licenses.md). Pour les activer pour Enterprise Voice, vous pouvez utiliser Windows PowerShell. Par exemple, exécutez :  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Pour en savoir plus sur Office 365 appelant Plans, voir le [système téléphonique et Plans de l’appel](calling-plan-landing-page.md) et [Appel des Plans pour Office 365](calling-plans-for-office-365.md).

- Vous pouvez uniquement attribuer payants et les numéros de téléphone gratuit service que vous avez obtenu dans le **Centre d’administration de Microsoft équipes** ou transférés à partir d’un autre fournisseur de services aux files d’attente des appels système téléphonique. Pour obtenir et utiliser des numéros gratuits service, vous devez configurer les crédits de Communications.

    > [!NOTE]
    > Numéros de téléphone de l’utilisateur (abonné) ne peut pas être affectés à appeler des files d’attente - le service seulement payant ou numéros de téléphone peuvent être utilisés.
  
- Lorsque vous distribuez les appels entrants à partir d’une file d’attente des appels système téléphonique, ces clients sont pris en charge pour les agents d’appel :

  - Skype pour le client de bureau Business 2016 (versions 32 et 64 bits)

  - Client de bureau Lync 2013 (versions 32 et 64 bits)

  - Tous les modèles de téléphone IP pris en charge pour Microsoft Teams. Consultez [Obtention de numéros de téléphone pour Skype Entreprise Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).

  - Mac Skype pour Client d’entreprise (version 16.8.196 et versions ultérieures)

  - Android Skype pour Client d’entreprise (version 6.16.0.9 et versions ultérieures)

  - iPhone Skype pour Client d’entreprise (version 6.16.0 et versions ultérieures)

  - iPad Skype pour Client d’entreprise (version 6.16.0 et versions ultérieures)

  - Client Microsoft équipes Windows (versions 32 et 64 bits)

  - Client Microsoft équipes Mac

  - Microsoft Teams iPhone application

  - Les équipes Microsoft pour Android

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Étape 2 : obtention ou transfert payant ou des numéros de téléphone gratuit service

Avant de pouvoir créer et configurer les files d'attente, vous devrez transférer vos numéros payants et gratuits existants. Une fois que vous obtenez les numéros de téléphone gratuit service payant, ils s’affichent dans le **Centre d’administration de Microsoft équipes** > **vocale** > **numéros de téléphone**et la volonté de **type numérique** présent figurer en tant que **Service - gratuit**. Pour obtenir vos numéros de service, voir les [numéros de téléphone de mise en service](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) , ou si vous souhaitez transférer un numéro de service existant, voir les [numéros de téléphone transfert vers Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Si vous êtes en dehors des États-Unis, vous ne pouvez pas utiliser le centre d’administration Microsoft Teams pour obtenir les numéros de service. Accédez à [Gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) à la place pour voir comment le faire à partir de l’extérieur des États-Unis.

Si vous configurez également les standards automatiques, vous devrez uniquement affecter un numéro de téléphone pour le compte du service de surveillance automatique principal de la ressource, puis d’appelants directs à votre file d’attente de l’appel. Si tel est le cas, la file d’attente d’appel vous devrez être créé avant de pouvoir créer une option dans le standard automatique de sélectionne la file d’attente de l’appel.
  
## <a name="step-3---create-a-new-call-queue"></a>Étape 3 : créer une nouvelle file d’attente d’appel

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> Chaque file d’attente de l’appel doit posséder un [compte de ressource](manage-resource-accounts.md)associé. Vous devez d’abord créer le compte de ressources, puis vous pouvez l’associer à la file d’attente de l’appel.

### <a name="using-the-microsoft-teams-admin-center"></a>À l’aide du centre d’administration Microsoft Teams

Dans le **Centre d’administration de Microsoft équipes**, **voix** >  **files d’attente des appels**, puis cliquez sur **+ Nouveau**:

### <a name="set-the-call-queue-display-name-and-resource-account"></a>Définir le complet de file d’attente appel qu’un compte nom et des ressources

![Configuration d’une file d’attente de l’appel.](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

![N ° 1](media/sfbcallout1.png)
**nom** Entrez un nom d’affichage de la description de la file d’attente de l’appel. Cela est nécessaire et peut contenir jusqu'à 64 caractères, espaces compris.

 Ce nom s’affichera dans la notification de l’appel entrant.

* * *

![Numéro 2](media/sfbcallout2.png)

**Ajouter des comptes** Sélectionnez un compte de ressource. Le compte de la ressource peut être ou non associé à un numéro payant service ou le numéro de téléphone gratuit pour la file d’attente de l’appel, mais chaque file d’attente d’appel requiert un compte de ressource.

Si il n’existe pas dans la liste, vous devez obtenir les numéros de service et les affecter à un compte de ressource avant de pouvoir créer cette file d’attente de l’appel, comme décrit précédemment. Pour obtenir vos numéros de service, voir les [numéros de téléphone de mise en service](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json). Vous devez créer un compte de ressource, comme décrit dans [Gérer les comptes de ressources dans les équipes](manage-resource-accounts.md) si vous souhaitez que votre file d’attente de l’appel vers un numéro de téléphone associé.

> [!NOTE]
> Si vous souhaitez ou que vous devez lui assigner un **domaine** ferait en l’affectant au compte de ressources pour la file d’attente de l’appel.

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Définir le message d’accueil et la musique joué suspendu

![Configuration d’une file d’attente de l’appel.](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
* * *

![Numéro 1](media/sfbcallout1.png)

**Message d’accueil** est facultative. Il s’agit du message d’accueil qui est diffusé aux utilisateurs d’appel dans le nombre de file d’attente d’appel.

Vous pouvez télécharger un fichier audio (format .wav, .mp3 ou .wma).

![Numéro 2](media/sfbcallout2.png)

**Musicale** Vous pouvez utiliser la musique par défaut en attente fournie avec la file d’attente de l’appel, ou vous pouvez télécharger un fichier audio .wav ou .wma mp3 formats à utiliser en tant que votre musique personnalisée en attente.

* * *

### <a name="select-the-call-answering-options"></a>Sélectionnez l’options de répondeur automatique

![Indique l’appel de méthode options de distribution](media/5d249515-d532-4af2-90da-011404028b89.png)

![Numéro 1](media/sfbcallout1.png)

Vous pouvez sélectionner jusqu'à 200 agents appel appartenant à des listes de diffusion spécifiées ou des groupes. Agents d’appel doivent être :

- Un utilisateur en ligne avec une licence de **Système téléphonique** et activé pour Enterprise Voice ou avec un Plan de l’appel.

  > [!NOTE]
  > Pour rediriger les appels vers des personnes dans votre organisation en ligne, ils doivent disposer d’une licence de **Système téléphonique** et être activés pour Enterprise Voice ou un Plan de l’appel. Voir [Assigner de Skype pour les licences d’entreprise](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) ou [licences attribuer les équipes Microsoft](assign-teams-licenses.md).

 Pour les activer pour Enterprise Voice, vous pouvez utiliser Windows PowerShell. Par exemple, exécutez :  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- Utilisateurs en ligne avec une licence de **Système téléphonique** et un Plan d’appel qui sont ajoutés à un groupe d’Office 365, une liste de Distribution à extension messagerie ou un groupe de sécurité. Il peut prendre jusqu'à 30 minutes pour un nouvel agent ajouté pour une liste de distribution ou un groupe de sécurité pour commencer à recevoir des appels à partir d’une file d’attente de l’appel. Un groupe de sécurité ou de la liste de distribution nouvellement créé peut prendre jusqu'à 48 heures soit disponible pour être utilisé avec les files d’attente de l’appel. Nouvellement créé Office 365 groupes sont presque immédiatement disponibles.

![Configurer les files d’attente de l’appel.](media/skype-for-business-add-agents-to-call-queue.png)

![Numéro 2](media/sfbcallout2.png)

**Méthode de routage** Vous pouvez choisir soit **Attendant**, **série**ou **tourniquet (Round Robin)** pour la méthode de distribution en file d’attente de votre appel. Toutes les files d’attente de nouveaux et existants appel aura attendant routage sélectionnée par défaut. Lorsque le routage standard est utilisé, le premier appel dans la file d’attente tous les agents appel sonnera en même temps. Le premier agent d’appel pour identifier l’appel Obtient l’appel.

- **Surveillance du routage** entraîne le premier appel dans la file d’attente pour faire sonner tous les agents d’appel en même temps. Le premier agent d’appel pour identifier l’appel Obtient l’appel.
- **Le routage de série** entraîne les appels entrants vers la sonnerie d’appel agents un par un, à partir du début de la liste d’appels de l’agent. Si un agent fait disparaître ou ne récupère pas d’un appel, l’appel sonnera l’agent suivant dans la liste et essayez de tous les agents un par un jusqu'à ce qu’elle est choisie ou délai d’attente dans la file d’attente.
  > [!NOTE]
  > Ce type de routage ignore les agents qui sont **en mode hors connexion**, qui ont la valeur leur présence **ne pas déranger**ou ont **choisi** de recevoir des appels à partir de cette file d’attente.
- **Round robin** répartit le routage des appels entrants afin que chaque agent appel le même nombre d’appels à partir de la file d’attente. Cela peut être très souhaitable dans un environnement de vente entrant afin de garantir l’opportunité égale entre tous les agents de l’appel.

### <a name="select-an-agent-opt-out-option"></a>Sélectionnez un agent exclure option

![Case à cocher indique que l’agent d’abonnement](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
* * *

![Numéro 1](media/sfbcallout1.png)

**Agent exclure option** Vous pouvez choisir d’autoriser les agents de file d’attente d’appel refuser de prendre des appels à partir d’une file d’attente spécifique en sélectionnant **l’Option Refuser l’Agent**.

L’activation de cette option permet de seront tous les agents de cette file d’attente pour démarrer ou arrêter de recevoir des appels à partir de cette file d’attente de l’appel à. Vous pouvez révoquer le privilège d’annulations agent à tout moment en désactivant la case à cocher, à l’origine des agents sont automatiquement accrédité pour cette file d’attente à nouveau (paramètre par défaut pour tous les agents).

Pour accéder à l’option exclure, les agents peuvent procédez comme suit :

 1. Ouvrez **les Options** dans leur bureau Skype pour client d’entreprise.
 2. Sous l’onglet **Transfert d’appel** , cliquez sur le lien **Modifier les paramètres en ligne** .
 3. Dans la page de paramètres utilisateur, cliquez sur **Appeler les files d’attente**, puis désactivez les cases à cocher des files d’attente pour lesquelles ils souhaitent sortir.

    > [!NOTE]
    > Agents à l’aide de Mac, mobile, ou clients Lync 2013 ou les utilisateurs de voix hybride qui sont hébergés sur site à l’aide de Skype pour serveur Business 2015, peut atteindre [https://aka.ms/cqsettings](https://aka.ms/cqsettings) pour accéder à l’abonnement option.

![N ° 2](media/sfbcallout2.png)
**paramètre d’alerte de l’Agent**

Définit la durée d’un agent être averti d’un appel avant le numéro de série ou tourniquet (Round Robin) des méthodes de routage déplacement vers l’agent suivant.

Le paramètre par défaut est de 30 secondes, mais elle peut être définie pour 3 minutes.

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a>Définir des options de gestion de l’appel de dépassement de capacité et délai d’expiration

![Configurer une file d’attente de l’appel.](media/3f018734-16fe-458b-827d-71fc25155cde.png)
  
* * *

![Numéro 1](media/sfbcallout1.png)

**Nombre maximal des appels dans la file d’attente** Permet de définir les appels maximales qui peuvent attendre dans la file d’attente en même temps. La valeur par défaut est 50, mais elle compris entre 0 et 200. Lorsque cette limite est atteinte, l’appel sera géré de façon que vous avez défini le paramètre **lorsque le nombre maximal d’appels est atteint** ci-dessous.

* * *

![Numéro 2](media/sfbcallout2.png)

**Lorsque le nombre maximal d’appels est atteint.** Lorsque la file d’attente d’appels atteint sa taille maximale (définie à l’aide de la valeur **maximale des appels dans la file d’attente** ), vous pouvez choisir que se passe-t-il au nouvel appel entrant.

- **Se déconnecter** L’appel sera déconnecté.
- **Rediriger vers** Lorsque vous choisissez cette option, sélectionnez une des options suivantes :

  - **Personne de votre société** Un utilisateur en ligne avec une licence de **Système téléphonique** et être activé pour Enterprise Voice ou possèdent un Plan de l’appel. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour ce faire, sélectionnez une **personne de votre société** et définissez cette personne pour que leurs appels transférés directement vers la messagerie vocale.

  Pour plus d’informations sur les licences requises pour la messagerie vocale, voir [configuration de la messagerie vocale dans le nuage](set-up-phone-system-voicemail.md).

  - **Application vocale** Sélectionnez le nom de l’une file d’attente de l’appel ou qui a déjà été créée standard automatique.

* * *

![Nombre 3](media/sfbcallout3.png)

**Délai d’attente des appels : temps d’attente maximal** Vous pouvez également choisir combien de temps un appel peut être en attente dans la file d’attente avant qu’il arrive à expiration et doit être redirigé ou déconnecté. Où elle sera redirigée est basée sur la façon dont vous définissez le paramètre **lorsqu’un appel arrive à expiration** . Vous pouvez définir une durée de 0 à 45 minutes.

Peut avoir la valeur du délai d’attente en secondes, toutes les 15 secondes. Cela vous permet de manipuler le flux des appels avec une plus fine granularité. Par exemple, vous pouvez spécifier que tous les appels qui sont sans réponse dans les 30 secondes par un agent d’accéder à un standard automatique de recherche dans l’annuaire.

![Numéro 4](media/sfbcallout4.png)

**Lorsque le délai d’attente expire** Lorsque l’appel atteint la limite que vous définissez le paramètre de **la durée pendant laquelle un appel peut attendre dans la file d’attente** , vous pouvez choisir que se passe-t-il à cet appel :

- **Se déconnecter** L’appel sera déconnecté.
- **Cet appel de redirection** Lorsque vous choisissez cette option, vous devez ces options :
  - **Personne de votre société** Un utilisateur en ligne avec une licence de **Système téléphonique** et être activé pour Enterprise Voice ou possèdent des Plans de l’appel. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour ce faire, sélectionnez une **personne de votre société** et définissez cette personne pour que leurs appels transférés directement vers la messagerie vocale.

  Pour plus d’informations sur les licences requises pour la messagerie vocale, voir [configuration de la messagerie vocale dans le nuage](set-up-phone-system-voicemail.md).

  - **Application vocale** Sélectionnez le nom de l’une file d’attente de l’appel ou qui a déjà été créée standard automatique.

## <a name="changing-a-users-caller-id-for-outbound-calls"></a>Modification des ID de l’appelant d’un utilisateur pour les appels sortants 

Vous pouvez protéger l’identité d’un utilisateur en modifiant son ID d’appelant pour les appels sortants vers une file d’attente d’appel, de standard automatique ou de n’importe quel nombre de service au lieu de cela en créant une stratégie à l’aide de l’applet de commande **New-CsCallingLineIdentity** .

Pour ce faire, exécutez :

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Ensuite, appliquer la stratégie à l’utilisateur à l’aide de l’applet de commande **Grant-CallingLineIdentity** . Pour ce faire, exécutez :
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Vous pouvez obtenir plus d’informations sur la façon d’apporter des modifications aux paramètres d’ID de l’appelant dans votre organisation dans l’article [ID d’appelant utilisation dans votre organisation](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization).
  
## <a name="want-to-know-more"></a>Vous souhaitez en savoir plus ?

Vous pouvez également utiliser Windows PowerShell pour créer et configurer des files d’attente de l’appel.
  
### <a name="call-queue-cmdlets"></a>Cmdlets de file d’attente

Voici les applets de commande dont vous avez besoin pour gérer une file d’attente de l’appel.
  
- [Nouvelle CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a>Informations supplémentaires sur PowerShell Windows

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Office 365 et Teams Microsoft à l’aide d’un point unique d’administration qui peut simplifier votre travail quotidien, lorsque vous avez plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :

  - [Présentation de Windows PowerShell et Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell présente de nombreux avantages dans vitesse, la simplicité et la productivité sur qu’à l’aide du centre d’administration Microsoft Teams tels que lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :

  - [Gérer Office 365 avec Windows PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Rubriques connexes

[Voici les avantages du système téléphonique dans Office 365](here-s-what-you-get-with-phone-system.md)

[Obtention de numéros de téléphone de service](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[Disponibilité des forfaits d'appels et de l’audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Nouvelle CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
