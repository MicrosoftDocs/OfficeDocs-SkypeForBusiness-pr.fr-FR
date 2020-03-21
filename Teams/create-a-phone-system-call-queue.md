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
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
description: Apprenez à configurer le système téléphonique pour les files d’attente d’appels Cloud avec Microsoft Teams.
ms.openlocfilehash: fc958aa1713a7cda12a054b3a029bfc1786b0955
ms.sourcegitcommit: 92a278c0145798266ecbe052e645b2259bcbd62d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42897247"
---
# <a name="create-a-cloud-call-queue"></a>Créer une file d’attente d’appels cloud

Les files d’attente d’appels Cloud peuvent fournir :

- Message d’accueil.
- Musique pendant que les personnes sont en attente.
- La redirection des appels vers des téléopérateurs dans des listes de distribution et des groupes de sécurité à extension messagerie.
- Définir des paramètres différents, tels que la taille maximale de la file d’attente, le délai d’expiration et les options de traitement des appels.
- Boîte vocale partagée permettant aux appelants de laisser un message à une organisation.

Vous n’associez pas directement un numéro de téléphone à une file d’attente d’appels, mais le numéro de téléphone est associé à un [compte de ressources](manage-resource-accounts.md). Une file d’attente d’appels peut être numérotée directement ou consultée par une sélection dans un standard automatique.

L’appelant entend lire de la musique pendant qu’il est en attente et l’appel se connecte à la *première fois, première sortie* (FIFO).

Tous les appels dans la file d’attente sont envoyés aux agents par le biais de l’une des méthodes suivantes :

- Avec le routage de l’attendant, le premier appel dans la file d’attente sonne sur tous les agents en même temps.
- Avec le routage en série, le premier appel dans la file d’attente sonne tous les agents d’appel un par un.
- Avec la répétition alternée, le routage des appels entrants est équilibré de telle sorte que chaque agent d’appel obtient le même nombre d’appels à partir de la file d’attente.

    > [!NOTE]
    > Les téléopérateurs qui sont **hors ligne**, ont défini leur présence sur **ne pas déranger** ou ont désactivé la file d’attente des appels ne recevront aucun appel.

- Une seule notification d’appel entrant (pour l’appel en tête de file) sera envoyée aux téléopérateurs à la fois.
- Lorsqu’un téléopérateur accepte l’appel, le prochain appel entrant dans la file d’attente sonnera pour les autres téléopérateurs.

> [!NOTE]
> Cet article s’applique à Microsoft teams et à Skype entreprise online.

## <a name="step-1--get-started"></a>Étape 1 : prendre en main

Pour commencer à utiliser les files d’attente d’appels, il est important de garder à l’esprit les points suivants :

- Une file d’attente d’appels doit avoir un compte de ressources associé. Pour plus d’informations sur les comptes de ressources, voir [gérer les comptes de ressources dans teams](manage-resource-accounts.md) .
- Lorsque vous attribuez un numéro de téléphone à un compte de ressources, vous pouvez désormais utiliser la [licence utilisateur virtuel](teams-add-on-licensing/virtual-user.md)du système téléphonique sans frais. Le système téléphonique autorise les numéros de téléphone au niveau de l’Organisation pour une standardisation automatique et des services de files d’attente de faible coût.

> [!NOTE]
> Les numéros de service de routage direct pour les files d’attente d’appels sont pris en charge pour les utilisateurs et agents Microsoft teams uniquement.

> [!NOTE]
> Pour rediriger les appels vers des utilisateurs de votre organisation qui sont en ligne, ils doivent disposer d’une licence de **système téléphonique** et être activés pour Enterprise Voice ou disposer d’offres d’appels d’Office 365. Voir [attribuer des licences Microsoft teams](assign-teams-licenses.md). Pour les activer pour Enterprise Voice, vous pouvez utiliser Windows PowerShell. Par exemple, exécutez :`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- Pour en savoir plus sur les offres d’appels d’Office 365, voir [système téléphonique et](calling-plan-landing-page.md) offres d’appel et [forfaits pour Office 365](calling-plans-for-office-365.md).

- Vous ne pouvez attribuer des files d’attente d’appels Cloud qu’aux numéros de téléphone de service gratuits ou payants que vous avez dans le **Centre d’administration Microsoft teams** ou transférés à partir d’un autre fournisseur de service. Les crédits de communication sont requis pour les numéros de service gratuits.

    > [!NOTE]
    > Les numéros de téléphone des utilisateurs (abonnés) ne peuvent pas être attribués aux numéros de service de file d’attente d’appels uniquement ou les numéros de téléphone gratuits peuvent être utilisés.

- Les clients suivants sont pris en charge pour les agents d’appel associés à une file d’attente d’appels Cloud :

  - Client de bureau Skype entreprise 2016 (versions 32 bits et 64 bits)

  - Client de bureau Lync 2013 (versions 32 bits et 64 bits)

  - Tous les modèles de téléphone IP pris en charge par Microsoft Teams. Consultez [Obtention de numéros de téléphone pour Skype Entreprise Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).

  - Client Skype entreprise pour Mac (version 16.8.196 et versions ultérieures)

  - Client Skype entreprise Android (version 6.16.0.9 et versions ultérieures)

  - Client Skype entreprise pour iPhone (version 6.16.0 et versions ultérieures)

  - Client Skype entreprise pour iPad (version 6.16.0 et versions ultérieures)

  - Client Microsoft Teams (versions 32 bits et 64 bits)

  - Client Microsoft teams Mac

  - Application Microsoft teams pour iPhone

  - Application Android Microsoft teams

    > [!NOTE]
    > Les files d’attente d’appels disposant d’un numéro de routage direct ne seront pas prises en charge pour les clients Skype entreprise, les clients Lync ou les téléphones IP Skype entreprise en tant qu’agents.

## <a name="step-2--get-or-transfer-toll-or-toll-free-service-phone-numbers"></a>Étape 2 : obtenir ou transférer des numéros de service gratuits ou payants

Pour pouvoir créer et configurer vos files d’attente d’appels, vous devez obtenir ou transférer vos numéros de service gratuits ou payants existants. Pour obtenir vos numéros de service, reportez-vous à la rubrique [obtention de numéros de service](getting-service-phone-numbers.md) ou, si vous souhaitez transférer un numéro de service existant, reportez-vous à la section transférer des [numéros de téléphone vers Office 365](phone-number-calling-plans/transfer-phone-numbers-to-teams.md). Une fois que vous avez obtenu les numéros de téléphone de service gratuits ou payants, ils s’affichent dans les**numéros de téléphone****vocaux** > du centre > d' **administration Microsoft teams**. Les numéros gratuits seront répertoriés avec un **type** de **service**numéro gratuit.

> [!NOTE]
> Si vous résidez en dehors des États-Unis, vous ne pouvez pas utiliser le centre d’administration de Microsoft teams pour obtenir des numéros de service. Pour plus d’informations sur la [gestion des numéros de téléphone de votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) , voir gérer les numéros de téléphone situés en dehors des États-Unis.

Lorsque vous configurez plusieurs standards automatiques, vous devez généralement affecter un numéro de téléphone au compte de ressources principal du standard automatique. Les comptes de ressources associés aux standards automatiques imbriqués ou aux files d’attente d’appels ne nécessitent généralement pas de numéros de téléphone. Ce standard automatique peut diriger les appelants vers vos files d’attente d’appels ou standards automatiques imbriqués, même s’ils n’ont pas de numéro de téléphone. Dans ces situations, vous pouvez créer tous les standards automatiques et les files d’attente d’appels dans votre système sans affecter d’options de clavier numérique, puis modifier les paramètres par la suite. Une file d’attente d’appels ou un standard automatique doit exister pour le configurer en tant qu’option de menu.

## <a name="step-3--create-a-call-queue"></a>Étape 3 : création d’une file d’attente d’appels

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> Chaque file d’attente d’appels doit avoir un [compte de ressources](manage-resource-accounts.md)associé. Vous devez d’abord créer le compte de ressources, puis vous pouvez l’associer à la file d’attente d’appels.

### <a name="use-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft teams

Dans le **Centre d’administration de Microsoft teams**, les**files d’attente d’appels** **vocaux** > , puis cliquez sur **+ Ajouter nouveau**:

### <a name="set-the-display-name-and-resource-account"></a>Définir le nom d’affichage et le compte de ressources

![Capture d’écran d’une nouvelle file d’attente d’appels avec des légendes numérotées](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

![Icône du numéro 1, référence une légende dans le](media/teamscallout1.png)
**nom** de la capture d’écran précédente entrez un nom descriptif pour la file d’attente d’appels. Ce nom est obligatoire et peut contenir jusqu’à 64 caractères, y compris des espaces.

 Ce nom s’affiche dans la notification de l’appel entrant.

* * *

![Dans la boîte de dialogue numéro 2, fait référence à une légende](media/teamscallout2.png)
dans la capture d’écran précédente**Ajouter des comptes** sélectionnez un compte de ressources. Toutes les files d’attente d’appels doivent disposer d’un compte de ressources. Il n’est pas nécessaire d’avoir un numéro de téléphone payant ou gratuit pour les comptes de ressources.

S’il n’y figure pas, vous pouvez obtenir des numéros de service et les affecter à un compte de ressources avant de créer la file d’attente d’appels, comme décrit précédemment. Pour obtenir vos numéros de service, consultez la rubrique [obtention de numéros de téléphone de service](getting-service-phone-numbers.md). Pour plus d’informations sur l’affectation d’un numéro de téléphone, voir [gérer les comptes de ressources dans teams](manage-resource-accounts.md) .

> [!NOTE]
> Si vous souhaitez utiliser un **domaine** , vous devez l’attribuer au compte de ressources de la file d’attente d’appels.

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Définir le message d’accueil et la musique lue pendant la mise en attente

![capture d’écran des options de salutation et de musique, avec des légendes numérotées](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

![Icône du numéro 1, référence une légende dans la capture d’écran](media/teamscallout1.png)
suivante**message** d’accueil facultatif pour les personnes qui appellent le numéro de la file d’attente d’appels.

Vous pouvez charger un fichier audio (formats. wav,. mp3 ou. WMA).

![Icône du numéro 2, qui fait référence à une légende dans la](media/teamscallout2.png)
capture d’écran précédente**musique en attente** , vous pouvez utiliser la musique par défaut fournie avec la file d’attente d’appels. Vous pouvez également charger un fichier audio au format. wav,. mp3 ou. WMA à utiliser comme votre musique personnalisée en attente.

* * *

### <a name="select-the-call-answering-options"></a>Sélectionner les options de répondeur automatique

![Capture d’écran des options de répondeur automatique](media/5d249515-d532-4af2-90da-011404028b89.png) 

![Dans la capture d’écran du numéro 1, fait référence à une](media/teamscallout1.png)
légende dans la capture d’écran suivante :**opérateurs et groupes** pour ajouter directement des agents, sans les ajouter à un groupe, cliquez sur **Ajouter des utilisateurs**. Placez les agents individuels dans l’ordre dans lequel vous souhaitez qu’ils reçoivent l’appel. Vous pouvez ajouter jusqu’à 20 agents individuels (pour ajouter plus de 20, les placer dans un groupe).

Les appels sont d’abord routés vers des agents individuels, puis vers les agents en groupes. 

Vous pouvez sélectionner jusqu’à 200 opérateurs d’appel qui appartiennent à l’une des listes de diffusion ou groupes suivantes :

- Groupe Office 365
- Groupe de sécurité
- Liste de distribution

Les agents d’appel sélectionnés doivent être : 

- Utilisateurs en ligne avec une licence de système téléphonique et la voix entreprise activée 
- Utilisateurs en ligne avec un plan d’appels
- Utilisateurs de Skype entreprise sur site

  > [!NOTE]
  > Cela s’applique également si vous souhaitez rediriger les appels vers des utilisateurs de votre organisation qui sont en ligne. Ces personnes doivent disposer d’une licence de **système téléphonique** et d’une voix entreprise activée *ou* avoir un plan d’appels. Pour plus d’informations, reportez-vous à la section [affectation de licences Skype entreprise](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses), [attribution de licences Microsoft teams](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)ou le [plan d’appels qui vous convient ?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)

 Pour activer un agent pour voix entreprise, vous pouvez utiliser Windows PowerShell. Par exemple, exécutez :`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- Utilisateurs disposant d’une licence de **système téléphonique** ou d’une offre d’appels ajoutée à un groupe Office 365 ; Liste de distribution à extension messagerie ; ou un groupe de sécurité. Lorsque vous ajoutez un agent dans une liste de distribution ou un groupe de sécurité en tant qu’agent de file d’attente d’appels, le premier appel peut durer jusqu’à trois heures. Une liste de distribution ou un groupe de sécurité nouvellement créé peut nécessiter jusqu’à 48 heures de disponibilité pour une utilisation avec des files d’attente d’appels. Les nouveaux groupes Office 365 sont disponibles presque immédiatement.

- Si vos agents utilisent l’application Microsoft teams pour appeler des files d’attente, elles doivent être en mode TeamsOnly.

![Icône du numéro 2, qui fait référence à une légende dans la](media/teamscallout2.png)
**méthode de routage** de capture d’écran précédente, vous pouvez choisir l’une des options **standard**, **série**ou **tourniquet** comme méthode de distribution. Tout le reste et les files d’attente d’appels sont sélectionnés par défaut. Lorsque le routage standard est utilisé, le premier appel dans la file d’attente sonne sur tous les agents d’appel en même temps. Le premier agent d’appel pour décrocher l’appel obtient l’appel.

- Le routage de l' **attendant** entraîne le premier appel dans la file d’attente pour sonner tous les agents d’appel en même temps. Le premier agent d’appel pour décrocher l’appel obtient l’appel.
- **Routage en série** les appels entrants sonnent chacun d’eux, du début de la liste des agents d’appel. Les agents ne peuvent pas être commandés dans la liste des agents d’appel. Si un agent est rejeté ou ne décroche aucun appel, l’appel sonnera sur l’agent suivant et tentera d’essayer tous les agents jusqu’à ce qu’il soit décroché.
  > [!NOTE]
  > Avec le routage en série, pour les agents qui sont **hors ligne** ou qui ont défini leur présence sur **ne pas déranger**, l’appel est routé vers ces utilisateurs et ne parvient pas à se connecter à l’utilisateur indisponible, le routage vers l’agent suivant dans la liste des agents. Ce n’est pas le cas si l’agent **a désactivé** la réception des appels à partir de la file d’attente d’appels. Pour réduire l’intervalle de temps pendant lequel les appels sont acheminés vers l’agent suivant en ligne, le temps des alertes d’agent peut être réduit.
- **Tourniquet de tourniquet** qui achemine les appels entrants de telle sorte que chaque agent d’appel obtient le même nombre d’appels à partir de la file d’attente. Cela pourrait être souhaitable dans un environnement de ventes entrantes pour garantir l’égalité des chances entre tous les agents d’appel.

### <a name="select-an-agent-opt-out-option"></a>Sélectionner une option d’annulation d’agent

![Capture d’écran des options d’annulation d’agent, avec des légendes numérotées](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

![Icône du numéro 1, qui fait référence à une légende dans l'](media/teamscallout1.png)
agent de capture d’écran précédent**peut refuser les appels** , vous pouvez choisir d’autoriser les agents de files d’attente d’appels à refuser les appels d’une file d’attente particulière en activant cette option.

L’activation de cette option permet à tous les agents de cette file d’attente de démarrer ou d’arrêter de recevoir des appels à partir de la file d’attente d’appels. Vous pouvez révoquer les privilèges d’annulation de l’agent à tout moment en désactivant la case à cocher, pour que les agents le fassent automatiquement pour cette file d’attente (paramètre par défaut pour tous les agents).

Pour accéder à l’option d’annulation, les agents peuvent :

 1. Ouvrez les **options** de votre client Skype entreprise de bureau.
 2. Dans l’onglet **transfert d’appel** , cliquez sur le lien modifier les **paramètres en ligne** .
 3. Dans la page Paramètres d’utilisateur, cliquez sur **files d’attente d’appels**, puis désactivez les cases à cocher pour désactiver les files d’attente.

    > [!NOTE]
    > Les agents qui utilisent des applications ou des points de terminaison autres que le bureau Skype entreprise peuvent accéder à l’option d’annulation [https://aka.ms/cqsettings](https://aka.ms/cqsettings)du portail des paramètres utilisateur.
    >
    > Si les agents se trouvent dans des clients de bureau Microsoft Teams, ils peuvent refuser l’appel en utilisant les paramètres d’appel. 

![Icône du numéro 2, qui fait référence à une légende dans le](media/teamscallout2.png)
**paramètre alerte** de l’agent de capture d’écran précédent.

Cela définit la durée d’un appel de l’agent pour être averti de l’appel avant que les méthodes de routage par série ou par répétition alternées soient déplacées vers l’agent suivant.

Le paramètre par défaut est de 30 secondes, mais peut être configuré pour une durée de 3 minutes maximum.

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a>Définir les options de dépassement d’appel et de gestion des délais d’expiration

![Capture d’écran des options de traitement de dépassement de capacité, avec des légendes numérotées](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

![Icône du numéro 1, qui fait référence à une légende dans la](media/teamscallout1.png)
capture d’écran précédente pour les**appels dans la file d’attente** , utilisez cette valeur pour définir le nombre maximal d’appels qui peuvent patienter en même temps dans la file d’attente. La valeur par défaut est 50, mais elle peut varier entre 0 et 200. Lorsque cette limite est atteinte, l’appel est géré selon la configuration du paramètre **lorsque le nombre maximal d’appels est atteint** ci-dessous.

* * *

![Icône du numéro 2, qui fait référence à une légende dans la](media/teamscallout2.png)
capture d’écran précédente**lorsque le nombre maximum d’appels est atteint** lorsque la file d’attente atteint la taille maximale (définie à l’aide du paramètre **appels dans la file d’attente** ), vous pouvez choisir ce qu’il advient des nouveaux appels entrants.

- Se **déconnecter** L’appel est déconnecté.
- **Rediriger vers** Lorsque vous choisissez cette option, sélectionnez l’une des options suivantes :

  - **Personne de votre entreprise** Un utilisateur en ligne disposant d’une licence de **système téléphonique** et est activé pour voix entreprise ou avoir un plan d’appels. Vous pouvez la configurer de manière à ce que l’appelant puisse être dirigé vers la boîte vocale. Pour cela, sélectionnez une **personne au sein de votre entreprise** et configurez cette personne pour que les appels soient transférés directement à la boîte vocale.

  Pour en savoir plus sur les licences requises pour la boîte vocale, consultez la rubrique [configurer la messagerie vocale Cloud](set-up-phone-system-voicemail.md).

  - **Application vocale** Sélectionnez le nom d’un compte de ressources associé à une file d’attente d’appels ou à un standard automatique que vous avez déjà créé.

* * *

![Icône du numéro 3, qui fait référence à une légende dans la](media/teamscallout3.png)
capture d’écran précédente**délai d’appel : temps d’attente maximum** vous pouvez également décider du temps pendant lequel un appel peut être mis en attente dans la file d’attente avant qu’elle ne soit interrompue ou déconnectée. Le moment où il est redirigé dépend de la façon dont vous définissez le paramètre à la **fin de l’appel** . Vous pouvez définir une heure comprise entre 0 et 45 minutes.

La valeur Timeout peut être définie en secondes, à des intervalles de 15 secondes. Cela vous permet de manipuler le flux d’appels avec une granularité plus fine. Par exemple, vous pouvez spécifier que les appels qui ne sont pas traités par un agent dans un délai de 30 secondes s’exécutent dans un standard automatique de recherche d’annuaires.

![Icône du numéro 4, qui fait référence à une légende dans la](media/teamscallout4.png)
capture d’écran précédente lorsque le délai d’appel est**écoulé** lorsque l’appel atteint la limite définie en fonction de la **durée pendant laquelle un appel peut patienter dans la file d’attente** , vous pouvez choisir ce qu’il advient de l’appel :

- Se **déconnecter** L’appel est déconnecté.
- **Rediriger cet appel vers** Lorsque vous choisissez cette option, vous disposez des options suivantes :
  - **Personne de votre entreprise** Un utilisateur en ligne disposant d’une licence de **système téléphonique** et est activé pour voix entreprise ou avec des plans d’appels. Pour la configurer de manière à ce que la personne qui vous appelle puisse être envoyée à la boîte vocale, sélectionnez une **personne dans votre entreprise** et définissez cette personne de sorte que les appels soient transférés directement à la boîte vocale.

  Pour en savoir plus sur les licences requises pour la boîte vocale, consultez la rubrique [configurer la messagerie vocale Cloud](set-up-phone-system-voicemail.md).

  - **Application vocale** Sélectionnez le nom d’un compte de ressources associé à une file d’attente d’appels ou à un standard automatique que vous avez déjà créé.

## <a name="change-caller-id-for-outbound-calls"></a>Changer l’identification de l’appelant pour les appels sortants

Pour protéger l’identité d’un agent d’appel, modifiez son ID d’appelant pour les appels sortants vers une file d’attente d’appels, le standard automatique ou n’importe quel numéro de service avec l’applet **de commande New-CsCallingLineIdentity** , comme dans l’exemple suivant :

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Appliquez ensuite la stratégie à l’utilisateur à l’aide de l’applet de commande **Grant-CallingLineIdentity** comme dans l’exemple suivant : 

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Pour plus d’informations, reportez-vous à [utilisation de l’ID d’appelant au sein de votre organisation](/microsoftteams/how-can-caller-id-be-used-in-your-organization).

## <a name="call-queue-cmdlets"></a>Cmdlets de files d’attente d’appels

Vous pouvez également utiliser Windows PowerShell pour créer et configurer des files d’attente d’appels. Voici les applets de passe que vous utilisez pour gérer une file d’attente d’appels.

- [Nouveau-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a>Informations supplémentaires sur PowerShell Windows

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Windows PowerShell vous permet de gérer Office 365 et Microsoft teams avec un seul point d’administration. Cela peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour prendre en main Windows PowerShell, consultez ces rubriques :

  - [Présentation de Windows PowerShell et Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell offre de nombreux avantages en termes de rapidité, de simplicité et de productivité via le centre d’administration Microsoft teams lorsque vous apportez des modifications à de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :

  - [Gérer Office 365 avec Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Sujets associés

[Voici les avantages du système téléphonique dans Office 365](here-s-what-you-get-with-phone-system.md)

[Obtention de numéros de téléphone de service](getting-service-phone-numbers.md)

[Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Nouveau-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
