---
title: Créer une file d’attente des appels dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: Découvrez comment configurer des files d’attente d’appels pour les grandes organisations dans Microsoft Teams, qui fournit un message de salutation, des attentes musicales, la redirection d’appels et d’autres fonctionnalités.
ms.openlocfilehash: e7696878ba84942c2dcc88a1df3d5fc29144f883
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728733"
---
# <a name="create-a-call-queue"></a>Créer une file d’attente des appels

Les files d’attente des appels utilisent une méthode de routage des appelants, qui sont orientés vers les personnes de votre organisation qui pourront les aider à résoudre un problème ou répondre à une question. Les appels sont distribués les uns après les autres aux personnes présentes dans la file d’attente (appelées *agents*). 

> [!TIP]
> Cet article est pour les grandes organisations. Si votre organisation est une petite entreprise, lisez plutôt Créer une file d’attente [d’appels - Didacticiel](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) sur les petites entreprises.

Les files d’attente des appels fournissent :

- un message d’accueil.

- une musique pour les personnes en attente dans la file d’attente.

- un routage des appels vers les agents, en utilisant la méthode *Premier entré, premier sorti* (PEPS).

- Gestion des options pour le débordement et la temporisation des files d’attente.

Veillez à lire l’article [Planifier les standards automatiques et les files d’attente des appels pour Teams](plan-auto-attendant-call-queue.md), puis à suivre les [étapes de démarrage](plan-auto-attendant-call-queue.md#getting-started) avant de suivre les procédures de cet article.

## <a name="video-demonstration"></a>Démonstration vidéo

Cette vidéo montre un exemple de base de la création d’une file d’attente d’appels dans Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

## <a name="create-the-call-queue"></a>Créer la file d’attente d’appels

Pour configurer une file d’attente des appels, dans le centre d’administration Teams, développez **Voix**, cliquez sur **Files d’attente d’appels**, puis sur **Ajouter**.

Saisissez un nom pour la file d’attente des appels.

## <a name="resource-accounts"></a>Comptes de ressources

![Capture d’écran des paramètres du compte de ressource.](media/call-queue-name-language.png)

Cliquez sur **Ajouter des comptes**, recherchez le compte de ressource que vous souhaitez utiliser avec cette file d’attente des appels, cliquez sur **Ajouter**, puis de nouveau sur **Ajouter**. (Les agents verront le nom du compte de ressource lorsqu’ils recevront un appel entrant.)

Pour [plus d’Teams, voir Gérer Teams comptes](manage-resource-accounts.md) de ressources.

### <a name="assign-calling-id"></a>Affecter un ID d’appel

![Capture d’écran des paramètres d’ID d’appel.](media/call-queue-assign-calling-id.png)

Si vous envisagez d’utiliser un canal Teams pour vos télétribueurs, vous pouvez leur attribuer un numéro d’ID d’appelant sortant en spécifiant un ou plusieurs comptes de ressources avec un numéro de téléphone.

Cliquez **sur** Ajouter, recherchez les comptes de ressources que vous voulez autoriser les agents à appeler à des fins d’ID lors des appels sortants, cliquez sur **Ajouter,** puis sur **Ajouter.**

Si vous n’utilisez pas de canal Teams pour contrôler l’appartenance de l’agent, vous pouvez définir directement l’ID d’appelant pour les membres de la file d’attente d’appels sur le numéro de service de la file d’attente d’appels ou le personnel automatique approprié. Consultez l’article [Gérer les stratégies d’identification de l’appelant dans Microsoft Teams](caller-id-policies.md) pour en savoir plus.

## <a name="language"></a>Langue

![Capture d’écran des paramètres de langue.](media/call-queue-language.png)

Choisissez une [langue prise en charge](create-a-phone-system-call-queue-languages.md). Nous utiliserons cette langue pour les invites vocales générées par le système et la transcription de la messagerie vocale (si vous les activez).

## <a name="greetings-and-music-on-hold-in-queue"></a>Message d’accueil et musique de mise en attente dans la file d’attente

![Capture d’écran des salutations et de la musique mise en attente dans les paramètres de file d’attente.](media/call-queue-greetings-music.png)

Indiquez si vous souhaitez diffuser un message d’accueil aux appelants lorsqu’ils arrivent dans la file d’attente. Vous devez télécharger un fichier MP3, WAV ou WMA contenant le message d’accueil que vous souhaitez diffuser. La taille maximale de l’enregistrement téléchargé est de 5 Mo.

Teams fournit une musique par défaut aux appelants lorsqu’ils sont en attente dans une file d’attente. La musique par défaut fournie dans les files d’attente des appels Teams est exempte de toute redevance payable par votre organisation. Si vous souhaitez diffuser un fichier audio spécifique, choisissez **Lire un fichier audio** et téléchargez un fichier MP3, WAV ou WMA.

> [!NOTE]
> Vous êtes responsable de la suppression et de la sécurisation indépendantes de tous les droits et autorisations nécessaires pour utiliser tout fichier audio ou musical avec votre service Microsoft Teams groupe, qui peuvent inclure des droits de propriété intellectuelle et d’autres droits sur la musique, les effets sonores, l’audio, les marques de musique, les noms et autres contenus du fichier audio de tous les titulaires des droits concernés, à savoir des artistes, des acteurs, des acteurs, des produire, des produire, des composers, des étiquettes d’enregistrement, des éditeurs de musique, des éditeurs de musique, des clips, des bandes sonores, des droits de propriété collective et toute autre partie qui possède, contrôle ou licence les droits de copyright de la musique, les effets sonores, les audio et autres droits de propriété intellectuelle.

## <a name="call-agents"></a>Agents d’appel

Examinez les [conditions d’ajout des agents à une file d’attente ](plan-auto-attendant-call-queue.md#prerequisites).

![Capture d’écran des paramètres d’utilisateurs et de groupes pour les files d’attente d’appels.](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a>Canal Teams

Vous pouvez ajouter jusqu’à 200 agents via un canal Teams.

Si vous voulez [utiliser un canal Teams pour gérer la file d’attente](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e), sélectionnez l’option **Sélectionner une équipe**, puis cliquez sur **Ajouter un canal**. Recherchez l’équipe à utiliser, sélectionnez-la, puis cliquez sur **Ajouter**. Sélectionnez le canal que vous voulez utiliser (seuls les canaux standard sont pris en charge), puis cliquez **sur Appliquer.** Vous devez être membre de l’équipe, créateur ou propriétaire du canal.

Les clients suivants sont pris en charge lors de l’utilisation d Teams pour les files d’attente d’appels : 

  - Microsoft Teams Windows client
  - Client Microsoft Teams pour Mac

> [!NOTE]
> Si vous utilisez cette option, l’utilisation de la file d’attente d’appels peut prendre jusqu’à 24 heures.

##### <a name="users-and-groups"></a>Utilisateurs et groupes

Vous pouvez ajouter jusqu’à 20 agents individuellement et jusqu’à 200 agents via des groupes.

Si vous voulez ajouter des utilisateurs individuels ou des groupes à la file d’attente, sélectionnez l’option **Choisir des utilisateurs et des groupes**. 

Pour ajouter un utilisateur à la file d’attente, cliquez sur **Ajouter des utilisateurs**, recherchez l’utilisateur, cliquez sur **Ajouter**, puis de nouveau sur **Ajouter**.

Pour ajouter un groupe à la file d’attente, cliquez sur **Ajouter des groupes**, recherchez le groupe, cliquez sur **Ajouter**, puis sur **Ajouter**. Vous pouvez utiliser des listes de distribution, des groupes de sécurité et des groupes Microsoft 365 ou des équipes Microsoft Teams.

> [!NOTE]
> L’arrivée du premier appel peut prendre jusqu’à huit heures pour les nouveaux utilisateurs ajoutés à un groupe.

## <a name="call-routing"></a>Routage des appels

![Capture d’écran des paramètres du mode de conférence et de la méthode de routage.](media/call-queue-conference-mode-routing-method.png)

Le **mode conférence** réduit considérablement le temps nécessaire à la mise en relation d’un appelant avec un agent, une fois que l’agent a accepté l’appel. Pour que le mode conférence fonctionne, les agents de la file d’attente des appels doivent utiliser l’un des clients suivants :

  - la dernière version du client Microsoft Teams pour ordinateur de bureau, de l’application Android ou de l’application iOS
  - la version 1449/1.0.94.2020051601 ou une version ultérieure du téléphone Microsoft Teams
  
Les comptes Teams des agents doivent être définis sur le mode Teams uniquement. Les agents qui ne répondent pas aux exigences ne sont pas inclus dans la liste de routage des appels. Nous vous recommandons d’activer le mode conférence pour vos files d’attente des appels si tous vos agents utilisent des clients compatibles.

> [!NOTE]
> Le mode conférence n’est pas pris en charge si les appels téléphoniques sont acheminés vers la file d’attente à partir d’une passerelle de routage direct activée pour le routage en fonction de l’emplacement.

> [!TIP]
> Nous **vous recommandons** de définir le mode Conférence sur **Sur.**

La **méthode de routage** détermine l’ordre dans lequel les agents reçoivent les appels de la file d’attente. Sélectionnez l’une des options suivantes :

- Le **routage du standard** appelle tous les agents de la file d’attente en même temps. Le premier agent à prendre l’appel reçoit l’appel.

- Le **routage en série** appelle tous les agents d’appel les uns après les autres, dans l’ordre spécifié dans la liste des **Agents d’appel**. Si un agent rejette ou ne répond pas à un appel, l’appel sera transféré à l’agent suivant et à tous les agents jusqu’à ce que l’un deux réponde ou que le temps soit écoulé.

- Le **tourniquet (round robin)** équilibre le routage des appels entrants afin que chaque agent d’appel reçoive le même nombre d’appels provenant de la file d’attente. Ceci peut être utile dans un environnement de ventes entrantes pour assurer l’égalité des chances entre tous les agents d’appel.

- L’**inactivité la plus longue** achemine chaque appel vers l’agent qui a été inactif le plus longtemps. Un agent est considéré comme inactif si son état de présence est défini sur Disponible ou si son état de présence est défini sur Absent depuis moins de 10 minutes. Les agents dont l’état de présence est définie sur Absent depuis plus de 10 minutes ne sont pas considérés comme inactifs et ne pourront pas recevoir d’appels tant qu’ils n’auront pas changé leur présence en Disponible. 

> [!TIP]
> Il est recommandé de définir la **méthode de routage** sur **Rond-rond** ou **Inactif** le plus long.

![Capture d’écran des paramètres de routage, de désinspondage et d’heure d’alerte.](media/call-queue-presence-agents-time.png)

Le **routage basé sur la présence** utilise le statut de disponibilité des agents d’appel pour déterminer si un agent doit être inclus dans la liste de routage des appels pour la méthode de routage sélectionnée. Les agents d’appel dont le statut de disponibilité est défini sur **Disponible** sont inclus dans la liste de routage des appels et peuvent recevoir des appels. Les agents dont le statut de disponibilité est défini sur un autre statut sont exclus de la liste de routage des appels et ne recevront pas d’appels tant que leur statut de disponibilité ne sera pas défini sur **Disponible**. 

Vous pouvez activer le routage des appels basé sur la présence avec toutes les méthodes de routage.

Si un agent refuse de recevoir des appels, il ne sera pas inclus dans la liste de routage des appels, quel que soit son statut de disponibilité. 

> [!NOTE]
> Lorsque  l’inactivité la plus longue est sélectionnée comme méthode de routage, un routage basé sur la  présence est nécessaire et activé automatiquement, même si le basculement de routage en fonction de la présence est éteint et grisé.
>
> Si le routage basé sur la présence n’est pas activé et qu’il y a plusieurs appels dans la file d’attente, le système présentera ces appels simultanément aux agents, quel que soit leur statut de présence. Cela entraînera plusieurs notifications d’appels aux agents, en particulier si certains agents ne répondent pas à l’appel initial qui leur est présenté.
> 
> Les agents qui utilisent le client Skype Entreprise ne sont pas inclus dans la liste de routage des appels lorsque le routage basé sur la présence est activé. Si certains de vos agents utilisent Skype Entreprise, n’activez pas le routage des appels basé sur la présence.

> [!TIP]
> Il est recommandé de définir le **routage en fonction** de **la** présence vers Le.

La **durée de l’alerte pour un agent** spécifie la durée pendant laquelle le téléphone d’un agent sonnera avant que la file d’attente ne redirige l’appel vers l’agent suivant.

> [!TIP]
> Nous vous recommandons de définir la **durée d’alerte** de l’agent sur **20** secondes.

## <a name="call-overflow-handling"></a>Gestion du débordement des appels

![Capture d’écran des paramètres de dépassement de capacité d’appel.](media/call-queue-overflow-handling.png)

Le **nombre maximal d’appels dans la file d’attente** spécifie le nombre maximal d’appels pouvant attendre dans la file d’attente à tout moment. La valeur par défaut est de 50, mais elle peut être définie sur une valeur comprise entre 0 et 200. Lorsque cette limite est atteinte, l’appel est géré comme cela est indiqué par le paramètre **Lorsque le nombre maximum d’appels est atteint**.

Vous pouvez choisir de mettre fin à l’appel ou de le rediriger vers l’une des destinations de routage des appels. Par exemple, vous pouvez demander à l’appelant de laisser un message vocal pour les agents dans la file d’attente. Pour les transferts externes, veuillez vous reporter aux rubriques [Conditions préalables](plan-auto-attendant-call-queue.md#prerequisites) et [Transferts de numéros de téléphone externes : détails techniques](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) pour le formatage des numéros.

> [!NOTE]
> Si le nombre maximum d’appels est défini sur 0, le message d’accueil ne sera pas diffusé.

## <a name="call-timeout-handling"></a>Gestion de la temporisation des appels

![Capture d’écran des paramètres du délai d’appel.](media/call-queue-timeout-handling.png)

**Temporisation de l’appel : temps d’attente maximum** spécifie la durée maximum pendant laquelle un appel peut être mis en attente dans la file d’attente avant de le rediriger ou d’y mettre fin. Vous pouvez spécifier une valeur comprise entre 0 seconde et 45 minutes.

Vous pouvez choisir de mettre fin à l’appel ou de le rediriger vers l’une des destinations de routage des appels. Par exemple, vous pouvez demander à l’appelant de laisser un message vocal pour les agents dans la file d’attente. Pour les transferts externes, veuillez vous reporter aux rubriques [Conditions préalables](plan-auto-attendant-call-queue.md#prerequisites) et [Transferts de numéros de téléphone externes : détails techniques](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) pour le formatage des numéros.

Lorsque vous avez sélectionné vos options de temporisation des appels, cliquez sur **Enregistrer**.

## <a name="summary-of-recommended-call-queue-settings"></a>Résumé des paramètres recommandés de la file d’attente d’appels

Les configurations ci-dessous sont recommandées :

- **Mode conférence** sur **On**
- **Méthode de routage** sur **Tourniquet (round robin)** ou **Inactivité la plus longue**
- **Routage basé sur la présence** sur **Activé**
- **Durée de l’alerte pour un agent :** sur **20 secondes**

## <a name="supported-clients"></a>Clients pris en charge

Les clients suivants sont pris en charge pour les agents d’appel dans une file d’attente des appels :

  - Client Skype Entreprise 2016 pour ordinateur de bureau (versions 32 bits et 64 bits)
  - Client Lync 2013 pour ordinateur de bureau (versions 32 bits et 64 bits)
  - Tous les modèles de téléphone IP pris en charge pour Microsoft Teams. Consultez l’article [Obtenir des téléphones pour Skype Entreprise Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).
  - Client Skype Entreprise pour Mac (version 16.8.196 et versions ultérieures)
  - Client Skype Entreprise pour Android (version 6.16.0.9 et versions ultérieures)
  - Client Skype Entreprise pour iPhone (version 6.16.0 et versions ultérieures)
  - Client Skype Entreprise pour iPad (version 6.16.0 et versions ultérieures)
  - Client Windows Microsoft Teams (versions 32 bits et 64 bits)
  - Client Microsoft Teams pour Mac
  - Microsoft Teams [infrastructure de bureau virtualisé](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix et VMware)
  - Application Microsoft Teams pour iPhone
  - Application Microsoft Teams pour Android

    > [!NOTE]
    > Les files d’attente des appels auxquelles un numéro de routage direct est attribué ne prennent pas en charge les clients Skype Entreprise, les clients Lync ou les téléphones IP Skype Entreprise en tant qu’agents. Le Teams client n’est pris en charge qu’avec un mode de [co-existence Teams uniquement.](/microsoftteams/setting-your-coexistence-and-upgrade-settings)

## <a name="call-queue-cmdlets"></a>Cmdlets de files d’attente des appels

Vous pouvez également utiliser Windows PowerShell pour créer et configurer des files d’attente des appels. Voici les cmdlets utilisés pour gérer une file d’attente des appels.

- [New-CsCallQueue](/powershell/module/skype/new-CsCallQueue)

- [Set-CsCallQueue](/powershell/module/skype/set-CsCallQueue)

- [Get-CsCallQueue](/powershell/module/skype/get-CsCallQueue)

- [Remove-CsCallQueue](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a>Rubriques connexes

[Les avantages du système téléphonique](here-s-what-you-get-with-phone-system.md)

[Obtenir des numéros de téléphone de service](getting-service-phone-numbers.md)

[Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[New-CsOnlineApplicationInstance](/powershell/module/skype/new-csonlineapplicationinstance)

[Présentation de Windows PowerShell et Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
