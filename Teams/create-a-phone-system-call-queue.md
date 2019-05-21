---
title: Créer une file d’attente d’appel
ms.author: crowe
author: CarolynRowe
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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Apprenez à configurer le système téléphonique pour les files d’attente d’appels Cloud afin de vous donner un message d’accueil professionnel, de la musique en attente et de rediriger les appels d’appel vers des listes de distribution et des groupes de sécurité. Vous pouvez également définir la taille maximale de la file d’attente, le délai d’expiration et les options de traitement des appels.
ms.openlocfilehash: 63dc71d6fad4fa82e1a335b20612e60c3b56ac91
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281946"
---
# <a name="create-a-cloud-call-queue"></a>Créer une file d’attente d’appels cloud

Les files d’attente d’appels Cloud incluent des messages d’accueil qui sont utilisés lorsque quelqu’un vous appelle pour appeler un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la possibilité de rechercher le prochain agent d’appel disponible pour gérer l’appel alors que les personnes qui rejoignent les appels sont écouter de la musique pendant l’attente. Vous pouvez créer des files d’attente d’appels uniques ou multiples pour votre organisation.
  
Les files d’attente d’appels Cloud peuvent fournir:
  
- Un message d’accueil professionnel.
- Musique pendant que les personnes sont en attente.
- Redirection des appels vers des téléopérateurs dans des listes de distribution et des groupes de sécurité à extension messagerie.
- Création de paramètres pour la taille maximale de la file d’attente d’appels, le délai d’expiration et les options de traitement des appels.

Lorsque quelqu’un vous appelle pour appeler un numéro de téléphone associé à une file d’attente d’appels via un [compte de ressource](manage-resource-accounts.md), il entend d’abord un message d’accueil (s’il y a une configuration), puis il est placé dans la file d’attente et attend que le prochain agent d’appel soit disponible. La personne qui appelle entend entendre de la musique alors qu’elle est en attente, et les appels sont proposés aux téléopérateurs pour la *première* fois (FIFO).
  
Tous les appels en attente dans la file d’attente seront distribués à l’aide de l’une des méthodes suivantes:
  
- Avec le routage de l’attendant, le premier appel dans la file d’attente sonne sur tous les agents en même temps.
- Lorsque le routage est en série, le premier appel dans la file d’attente sonne sur tous les agents d’appel un par un.
- Avec la répétition alternée, le routage des appels entrants est équilibré de telle sorte que chaque agent d’appel puisse obtenir le même nombre d’appels à partir de la file d’attente.

    > [!NOTE]
    > Les téléopérateurs qui sont **hors ligne**, ont défini leur présence sur **ne pas** déranger ou ont désactivé la file d’attente d’appels.
  
- Une seule notification d’appel entrant (pour l’appel en tête de file) sera envoyée aux téléopérateurs à la fois.
- Lorsqu’un téléopérateur accepte l’appel, le prochain appel entrant dans la file d’attente sonnera pour les autres téléopérateurs.

> [!NOTE]
> Cet article s’applique à Microsoft teams et à Skype entreprise online.

## <a name="step-1---get-started"></a>Étape 1: commencer

Pour commencer à utiliser les files d’attente d’appels, il est important de garder à l’esprit les points suivants:
  
- Une file d’attente d’appels doit avoir un compte de ressources associé. Pour plus d’informations sur les comptes de ressources, voir [gérer les comptes de ressources dans teams](manage-resource-accounts.md) .
- Si vous envisagez d’affecter un numéro d’acheminement direct, vous devez acquérir et attribuer les licences suivantes à \(votre compte de ressources Office 365 entreprise E1, E3 ou E5, à l’aide\)du composant additionnel du système téléphonique.
- Si vous affectez un numéro de service Microsoft à la place, vous devez acquérir et attribuer les licences suivantes à votre compte \(de ressources Office 365 entreprise E1, E3 ou E5, avec le module complémentaire du système téléphonique et un\)plan d’appels.
- Il vous suffit de créer une licence pour les comptes de ressources avec un numéro de téléphone qui leur est attribué. Dans une file d’attente d’appels ou de standards automatiques imbriqués, vous n’avez pas besoin de vous attribuer une licence au reste des standards automatiques ou des files d’attente d’appels s’ils ne disposent pas de numéros de téléphone associés. 

> [!NOTE] 
> Les numéros de service de routage direct pour le standard automatique et les files d’attente d’appels sont uniquement pris en charge pour les utilisateurs et les agents Microsoft Teams.

> [!NOTE] 
> Microsoft travaille sur un modèle de licence sans frais pour des applications telles que les standards automatiques de Cloud et les files d’attente d’appels, pour le moment, vous devez utiliser le modèle de gestion des licences utilisateur.

> [!NOTE]
> Pour rediriger les appels vers des utilisateurs de votre organisation qui sont en ligne, ils doivent disposer d’une licence de **système téléphonique** et être activés pour Enterprise Voice ou disposer d’offres d’appels d’Office 365. Consultez la rubrique [affectation de licences Skype entreprise](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) ou [affectation de licences Microsoft teams](assign-teams-licenses.md). Pour les activer pour Enterprise Voice, vous pouvez utiliser Windows PowerShell. Par exemple, exécutez :  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Pour en savoir plus sur les offres d’appels d’Office 365, voir [système téléphonique et](calling-plan-landing-page.md) offres d’appel et [forfaits pour Office 365](calling-plans-for-office-365.md).

- Vous ne pouvez attribuer que des numéros de service payants et gratuits que vous avez disponibles dans le **Centre d’administration Microsoft teams** ou que vous avez transférés d’un autre fournisseur de services vers des files d’attente d’appels Cloud. Pour obtenir et utiliser des numéros de service gratuits, vous devez configurer des crédits de communication.

    > [!NOTE]
    > Les numéros de téléphone des utilisateurs (abonnés) ne peuvent pas être attribués aux numéros de service de file d’attente d’appels uniquement ou les numéros de téléphone gratuits peuvent être utilisés.
  
- Lorsque vous distribuez les appels entrants depuis une file d’attente d’appels Cloud, ces clients sont pris en charge pour les téléopérateurs:

  - Client de bureau Skype entreprise 2016 (versions 32 et 64 bits)

  - Client de bureau Lync 2013 (versions 32 et 64 bits)

  - Tous les modèles de téléphone IP pris en charge par Microsoft Teams. Consultez [Obtention de numéros de téléphone pour Skype Entreprise Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).

  - Client Skype entreprise pour Mac (version 16.8.196 et versions ultérieures)

  - Client Skype entreprise Android (version 6.16.0.9 et versions ultérieures)

  - Client Skype entreprise pour iPhone (version 6.16.0 et versions ultérieures)

  - Client Skype entreprise pour iPad (version 6.16.0 et versions ultérieures)

  - Client Microsoft Teams (versions 32 et 64 bits)

  - Client Microsoft teams Mac

  - Application Microsoft teams pour iPhone

  - Application Android Microsoft teams

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Étape 2: réception ou transfert de numéros de service gratuits ou payants

Avant de pouvoir créer et configurer les files d'attente, vous devrez transférer vos numéros payants et gratuits existants. Une fois que vous avez obtenu les numéros de téléphone de service gratuits ou payants, ceux-ci apparaissent dans les**numéros de téléphone****vocaux** > du centre > d' **administration Microsoft teams**et le **type de numéro** mentionné est répertorié en tant que **service-** gratuit. Pour obtenir vos numéros de service, reportez-vous à la rubrique [obtention de numéros de service](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) ou, si vous souhaitez transférer un numéro de service existant, reportez-vous à la section transférer des [numéros de téléphone vers Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Si vous résidez en dehors des États-Unis, vous ne pouvez pas utiliser le centre d’administration de Microsoft teams pour obtenir des numéros de service. Pour plus d’informations sur la [gestion des numéros de téléphone de votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) , voir gérer les numéros de téléphone situés en dehors des États-Unis.

Si vous configurez également des standards automatiques, il est possible que vous n’ayez besoin d’affecter un numéro de téléphone au compte de ressources principal du standard automatique, puis de lui envoyer des appelants directs. Si tel est le cas, la file d’attente des appels doit être créée avant de pouvoir créer une option dans le standard automatique qui sélectionne la file d’attente d’appels.
  
## <a name="step-3---create-a-new-call-queue"></a>Étape 3: création d’une file d’attente d’appels

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> Chaque file d’attente d’appels doit avoir un [compte de ressources](manage-resource-accounts.md)associé. Vous devez d’abord créer le compte de ressources, puis vous pouvez l’associer à la file d’attente d’appels.

### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft teams

Dans le **Centre d’administration de Microsoft teams**, les**files d’attente d’appels** **vocaux** >  , puis cliquez sur **+ Ajouter nouveau**:

### <a name="set-the-call-queue-display-name-and-resource-account"></a>Définir le nom d’affichage de la file d’attente d’appels et le compte de ressources

![Configuration d’une file d’attente d’appels.](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

![](media/sfbcallout1.png)
**Nom** du numéro 1 Entrez un nom descriptif pour la file d’attente d’appels. Cela est obligatoire et peut contenir jusqu’à 64 caractères, y compris des espaces.

 Ce nom sera affiché dans la notification de l’appel entrant.

* * *

![Numéro 2](media/sfbcallout2.png)

**Ajouter des comptes** Sélectionnez un compte de ressources. Le compte de ressource est ou n’est pas associé à un numéro de service payant ou gratuit pour la file d’attente d’appels, mais chaque file d’attente d’appels nécessite un compte de ressources associé.

S’il n’y figure pas, vous devez obtenir des numéros de service et les affecter à un compte de ressources avant de pouvoir créer cette file d’attente d’appels, comme décrit précédemment. Pour obtenir vos numéros de service, consultez la rubrique [obtention de numéros de téléphone de service](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json). Vous devez créer un compte de ressources conformément aux instructions de la section [gérer les comptes de ressources dans teams](manage-resource-accounts.md) si vous souhaitez que votre file d’attente d’appels dispose d’un numéro de téléphone associé.

> [!NOTE]
> Le cas échéant, ou si vous avez besoin d’affecter un **domaine** , vous pouvez l’affecter au compte de ressources de la file d’attente d’appels.

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Définir le message d’accueil et la musique lue pendant la mise en attente

![Configuration d’une file d’attente d’appels.](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
* * *

![Numéro 1](media/sfbcallout1.png)

Le **message d’accueil** est facultatif. Il s’agit du message d’accueil qui est lu pour les personnes qui rejoignent le numéro de la file d’attente d’appels.

Vous pouvez charger un fichier audio (formats. wav,. mp3 ou. WMA).

![Numéro 2](media/sfbcallout2.png)

**Attente musicale** Vous pouvez utiliser l’attente de musique par défaut fournie avec la file d’attente d’appels ou vous pouvez charger un fichier audio au format. wav,. mp3 ou. WMA à utiliser comme votre musique personnalisée en attente.

* * *

### <a name="select-the-call-answering-options"></a>Sélectionner les options de répondeur automatique

![Affiche les options de méthode de distribution des appels](media/5d249515-d532-4af2-90da-011404028b89.png)

![Numéro 1](media/sfbcallout1.png)

Vous pouvez sélectionner jusqu’à 200 téléopérateurs appartenant à des listes de diffusion ou groupes spécifiés. Les agents d’appel doivent être:

- Un utilisateur en ligne disposant d’une licence de **système téléphonique** et activé pour voix entreprise ou avec un plan d’appels.

  > [!NOTE]
  > Pour rediriger les appels vers des utilisateurs de votre organisation qui sont en ligne, ils doivent disposer d’une licence de **système téléphonique** et être activées pour voix entreprise ou avoir un plan d’appels. Consultez la rubrique [affectation de licences Skype entreprise](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) ou [affectation de licences Microsoft teams](assign-teams-licenses.md).

 Pour les activer pour Enterprise Voice, vous pouvez utiliser Windows PowerShell. Par exemple, exécutez :  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- Utilisateurs en ligne disposant d’une licence de **système téléphonique** et d’un plan d’appels qui sont ajoutés à un groupe Office 365, une liste de distribution à extension messagerie ou un groupe de sécurité. L’ajout d’un nouvel agent à un nouvel agent pour une liste de distribution ou un groupe de sécurité à partir d’une file d’attente peut durer jusqu’à 3 heures. Une liste de distribution ou un groupe de sécurité nouvellement créé peut nécessiter jusqu’à 48 heures de disponibilité pour une utilisation avec des files d’attente d’appels. Les nouveaux groupes Office 365 sont disponibles presque immédiatement.

![Configurez des files d’attente d’appels.](media/skype-for-business-add-agents-to-call-queue.png)

![Numéro 2](media/sfbcallout2.png)

**Méthode de routage** Vous pouvez choisir **standard**, **série**ou **tourniquet** pour la méthode de distribution de votre file d’attente d’appels. La totalité des files d’attente d’appels nouvelles et existantes est activée par défaut. Lorsque le routage de l’assistance est utilisé, le premier appel dans la file d’attente sonne tous les agents d’appel en même temps. Le premier agent d’appel pour décrocher l’appel obtient l’appel.

- Le routage de l' **attendant** entraîne le premier appel dans la file d’attente pour sonner tous les agents d’appel en même temps. Le premier agent d’appel pour décrocher l’appel obtient l’appel.
- Les appels entrants de **routage en série** sonneront entre les agents un par un, en commençant par le début de la liste de l’agent d’appel. Les agents ne peuvent pas être commandés dans la liste des agents d’appel. Si un agent est rejeté ou ne décroche pas d’appel, l’appel sonnera sur l’agent suivant dans la liste et tentera d’avoir accès à tous les agents un par un jusqu’à ce qu’il soit décroché ou arrive à expiration dans la file d’attente.
  > [!NOTE]
  > Le routage en série ignorera les agents qui sont **hors ligne**, ont défini leur présence sur **ne pas**déranger ou a **refusé** d’obtenir des appels à partir de cette file d’attente.
- **Tourniquet alterne** le routage des appels entrants de telle sorte que chaque agent d’appel puisse obtenir le même nombre d’appels à partir de la file d’attente. Il est possible que cela soit très désirable dans un environnement de ventes entrantes pour garantir l’égalité des chances entre tous les agents d’appel.

### <a name="select-an-agent-opt-out-option"></a>Sélectionner une option de désactivation de l’agent

![Case à cocher Désactiver l’agent](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
* * *

![Numéro 1](media/sfbcallout1.png)

**Option de refus d’agent** Vous pouvez choisir d’autoriser les agents de files d’attente d’appels à désactiver les appels d’une file d’attente particulière en sélectionnant **l’option agent opt out**.

L’activation de cette option permet à tous les agents de cette file d’attente de démarrer ou d’arrêter de recevoir des appels à partir de la file d’attente d’appels. Vous pouvez révoquer les privilèges d’annulation de l’agent à tout moment en désactivant la case à cocher, pour que les agents le fassent automatiquement pour cette file d’attente (paramètre par défaut pour tous les agents).

Pour accéder à l’option d’annulation, les agents peuvent procéder comme suit:

 1. Ouvrez les **options** de votre client Skype entreprise de bureau.
 2. Dans l’onglet **transfert d’appel** , cliquez sur le lien modifier les **paramètres en ligne** .
 3. Dans la page Paramètres utilisateur, cliquez sur **files d’attente d’appels**, puis désactivez les cases à cocher correspondant aux files d’attente pour lesquelles elles doivent être refusées.

    > [!NOTE]
    > Les agents utilisant des applications ou des points de terminaison autres que le bureau Skype entreprise peuvent accéder à l’option option opt [https://aka.ms/cqsettings](https://aka.ms/cqsettings)du portail des paramètres utilisateur.

![Paramètre d'](media/sfbcallout2.png)
**alerte d’agent** numéro 2

Cela définit la durée d’un appel de l’agent pour être averti de l’appel avant que les méthodes de routage par série ou par répétition alternées soient déplacées vers l’agent suivant.

Le paramètre par défaut est de 30 secondes, mais peut être configuré pour une durée de 3 minutes maximum.

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a>Définir les options de dépassement d’appel et de gestion des délais d’expiration

![Configurer une file d’attente d’appels.](media/3f018734-16fe-458b-827d-71fc25155cde.png)
  
* * *

![Numéro 1](media/sfbcallout1.png)

**Nombre maximal d’appels dans la file d’attente** Utilisez cette valeur pour définir le nombre maximal d’appels qui peuvent attendre dans la file d’attente en même temps. La valeur par défaut est 50, mais elle peut varier entre 0 et 200. Lorsque cette limite est atteinte, l’appel est géré en procédant comme suit **lorsque le nombre maximal d’appels est atteint** ci-dessous.

* * *

![Numéro 2](media/sfbcallout2.png)

**Lorsque le nombre maximum d’appels est atteint** Lorsque la file d’attente des appels atteint sa taille maximale (définie en utilisant le **nombre maximal d’appels dans la file d’attente** ), vous pouvez choisir ce qu’il advient des nouveaux appels entrants.

- **** Se déconnecter L’appel sera déconnecté.
- **Rediriger vers** Lorsque vous choisissez cette option, sélectionnez l’une des options suivantes:

  - **Personne de votre entreprise** Un utilisateur en ligne disposant d’une licence de **système téléphonique** et est activé pour voix entreprise ou avoir un plan d’appels. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour cela, sélectionnez une **personne au sein de votre entreprise** et configurez cette personne pour que les appels soient transférés directement à la boîte vocale.

  Pour en savoir plus sur les licences requises pour la boîte vocale, consultez la rubrique [configurer la messagerie vocale Cloud](set-up-phone-system-voicemail.md).

  - **Application vocale** Sélectionnez le nom d’une file d’attente d’appels ou d’un standard automatique qui a déjà été créé.

* * *

![Nombre 3](media/sfbcallout3.png)

**Délai d’appel: délai d’attente maximum** Vous pouvez également décider du temps qu’un appel peut mettre en attente dans la file d’attente avant qu’il arrive à expiration, et qu’il doive être redirigé ou déconnecté. L’endroit où il sera redirigé dépend de la manière dont vous définissez le **délai d’appel** . Vous pouvez définir une heure comprise entre 0 et 45 minutes.

La valeur Timeout peut être définie en secondes, à des intervalles de 15 secondes. Cela vous permet de manipuler le flux d’appels avec une granularité plus fine. Par exemple, vous pouvez spécifier que les appels qui ne sont pas traités par un agent dans un délai de 30 secondes s’exécutent dans un standard automatique de recherche d’annuaires.

![Numéro 4](media/sfbcallout4.png)

**Lorsque** le délai d’appel est épuisé Lorsque l’appel atteint la limite définie en fonction de la **durée pendant laquelle un appel peut patienter dans la file d’attente** , vous pouvez choisir ce qu’il advient de cet appel:

- **** Se déconnecter L’appel sera déconnecté.
- **Rediriger cet appel vers** Lorsque vous choisissez cette option, vous disposez des options suivantes:
  - **Personne de votre entreprise** Un utilisateur en ligne disposant d’une licence de **système téléphonique** et est activé pour voix entreprise ou avec des plans d’appels. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour cela, sélectionnez une **personne au sein de votre entreprise** et configurez cette personne pour que les appels soient transférés directement à la boîte vocale.

  Pour en savoir plus sur les licences requises pour la boîte vocale, consultez la rubrique [configurer la messagerie vocale Cloud](set-up-phone-system-voicemail.md).

  - **Application vocale** Sélectionnez le nom d’une file d’attente d’appels ou d’un standard automatique qui a déjà été créé.

## <a name="changing-a-users-caller-id-for-outbound-calls"></a>Modification de l’ID d’appelant d’un utilisateur pour les appels sortants 

Vous pouvez protéger l’identité d’un utilisateur en modifiant son ID d’appelant pour les appels sortants vers une file d’attente d’appels, le standard automatique ou tout autre numéro de service en créant une stratégie à l’aide de l’applet **de nouvelle cmdlet New-CsCallingLineIdentity** .

Pour cela, exécutez:

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Appliquez ensuite la stratégie à l’utilisateur à l’aide de l’applet **de demande Grant-CallingLineIdentity** . Pour cela, exécutez:
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Pour plus d’informations sur la modification des paramètres d’identification de l’appelant au sein de votre organisation, consultez l’article [comment utiliser l’identification de l’appelant au sein de votre organisation](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization).
  
## <a name="want-to-know-more"></a>Vous souhaitez en savoir plus ?

Vous pouvez également utiliser Windows PowerShell pour créer et configurer des files d’attente d’appels.
  
### <a name="call-queue-cmdlets"></a>Cmdlets de files d’attente d’appels

Voici les applets de passe dont vous avez besoin pour gérer une file d’attente d’appels.
  
- [Nouveau-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a>Informations supplémentaires sur PowerShell Windows

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Windows PowerShell vous permet de gérer Office 365 et Microsoft teams à l’aide d’un point d’administration unique qui peut vous simplifier le travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour prendre en main Windows PowerShell, consultez ces rubriques :

  - [Présentation de Windows PowerShell et Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration de Microsoft Teams, par exemple, lorsque vous apportez des modifications à de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :

  - [Gérer Office 365 avec Windows PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Voir aussi

[Voici les avantages du système téléphonique dans Office 365](here-s-what-you-get-with-phone-system.md)

[Obtention de numéros de téléphone de service](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Nouveau-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
