---
title: Créer une file d’attente des appels dans Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
- Phone System - seo-marvel-apr2020
description: Découvrez comment configurer des files d’attente d’appels pour les grandes organisations dans Microsoft Teams, qui fournit un message d’accueil, de la musique de suspension, la redirection des appels et d’autres fonctionnalités.
ms.openlocfilehash: 4c23b03e75c9433bcf5af6d4a5aa57e81447a74d
ms.sourcegitcommit: 823ad7fe5f7a27f681c95b2d369ce2cbe71cfdfe
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2022
ms.locfileid: "64691459"
---
# <a name="create-a-call-queue"></a>Créer une file d’attente des appels

Les files d’attente des appels utilisent une méthode de routage des appelants, qui sont orientés vers les personnes de votre organisation qui pourront les aider à résoudre un problème ou répondre à une question. Les appels sont distribués les uns après les autres aux personnes présentes dans la file d’attente (appelées *agents*). 

> [!TIP]
> Cet article s’applique aux grandes organisations. Si votre organisation est une petite entreprise, lisez [plutôt le didacticiel Créer une file d’attente d’appels - Petite entreprise](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) .

Les files d’attente des appels fournissent :

- un message d’accueil.

- une musique pour les personnes en attente dans la file d’attente.

- un routage des appels vers les agents, en utilisant la méthode *Premier entré, premier sorti* (PEPS).

- Gestion des options pour le débordement et la temporisation des files d’attente.

Veillez à lire l’article [Planifier les standards automatiques et les files d’attente des appels pour Teams](plan-auto-attendant-call-queue.md), puis à suivre les [étapes de démarrage](plan-auto-attendant-call-queue.md#getting-started) avant de suivre les procédures de cet article.

**Pour plus d’informations, consultez la matrice [de compatibilité des fonctionnalités de file d’attente](#call-queue-feature-compatibility) d’appels ci-dessous.**

## <a name="video-demonstration"></a>Démonstration vidéo

Cette vidéo montre un exemple de base de la création d’une file d’attente d’appels dans Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

## <a name="create-the-call-queue"></a>Créer la file d’attente d’appels

Pour configurer une file d’attente des appels, dans le centre d’administration Teams, développez **Voix**, cliquez sur **Files d’attente d’appels**, puis sur **Ajouter**.

Saisissez un nom pour la file d’attente des appels.

## <a name="resource-accounts"></a>Comptes de ressources

![Capture d’écran des paramètres du compte de ressource.](media/call-queue-name-language.png)

Cliquez sur **Ajouter des comptes**, recherchez le compte de ressource que vous souhaitez utiliser avec cette file d’attente des appels, cliquez sur **Ajouter**, puis de nouveau sur **Ajouter**. (Les agents verront le nom du compte de ressource lorsqu’ils recevront un appel entrant.)

Pour plus d’informations, consultez [Gérer Teams comptes de ressources](manage-resource-accounts.md).

## <a name="dynamic-caller-id"></a>ID d’appelant dynamique

![Capture d’écran de l’appel des paramètres d’ID.](media/call-queue-assign-calling-id.png)

**Disponible pour Teams canal/utilisateurs de bureau appelants collaboratifs et Teams utilisateurs clients mobiles avec des files d’attente d’appels standard**

Vous pouvez affecter des numéros d’ID d’appelant sortant pour les agents en spécifiant un ou plusieurs comptes de ressources avec un numéro de téléphone. Les agents peuvent sélectionner le numéro d’ID d’appelant sortant à utiliser avec chaque appel sortant qu’ils effectuent.

Cliquez sur **Ajouter**, recherchez les comptes de ressources que vous souhaitez autoriser les agents à utiliser à des fins d’ID d’appelant lors des appels sortants, cliquez sur **Ajouter**, puis cliquez sur **Ajouter**.

**Files d’attente d’appels standard**

Pour Teams utilisateurs de bureau et les files d’attente d’appels standard envisagent de définir directement l’ID de l’appelant pour les membres de la file d’attente d’appels sur le numéro de service de la file d’attente d’appels ou le standard automatique approprié. Pour plus d’informations, consultez [Gérer les stratégies d’ID d’appelant dans Microsoft Teams](caller-id-policies.md).

> [!NOTE]
> Le compte de ressource utilisé à des fins d’appel d’ID doit avoir une licence d’utilisateur virtuel système Téléphonie Microsoft Teams et l’une des opérations suivantes doit être attribuée :
>
> - Une licence de forfait d’appels et un numéro de téléphone attribué
> - Un numéro de téléphone Operator Connect attribué
> - Une stratégie de routage vocal en ligne (l’attribution de numéros de téléphone est facultative lors de l’utilisation du routage direct)


## <a name="language"></a>Langue

![Capture d’écran des paramètres de langue.](media/call-queue-language.png)

Choisissez une [langue prise en charge](create-a-phone-system-call-queue-languages.md). Nous utiliserons cette langue pour les invites vocales générées par le système et la transcription de la messagerie vocale (si vous les activez).

## <a name="greetings-and-music-on-hold-in-queue"></a>Message d’accueil et musique de mise en attente dans la file d’attente

![Capture d’écran des messages d’accueil et de la musique en attente dans les paramètres de file d’attente.](media/call-queue-greetings-music.png)

Indiquez si vous souhaitez diffuser un message d’accueil aux appelants lorsqu’ils arrivent dans la file d’attente. Vous devez télécharger un fichier MP3, WAV ou WMA contenant le message d’accueil que vous souhaitez diffuser. La taille maximale de l’enregistrement téléchargé est de 5 Mo.

Teams fournit une musique par défaut aux appelants lorsqu’ils sont en attente dans une file d’attente. La musique par défaut fournie dans les files d’attente des appels Teams est exempte de toute redevance payable par votre organisation. Si vous souhaitez diffuser un fichier audio spécifique, choisissez **Lire un fichier audio** et téléchargez un fichier MP3, WAV ou WMA.

> [!NOTE]
> Vous êtes responsable de l’effacement indépendant et de la sécurisation de tous les droits et autorisations nécessaires pour utiliser n’importe quel fichier audio ou de musique avec votre service Microsoft Teams, qui peut inclure la propriété intellectuelle et d’autres droits dans toute musique, effets sonores, audio, marques, noms et autres contenus dans le fichier audio de tous les titulaires de droits pertinents, qui peuvent inclure des artistes, des acteurs,  interprètes, musiciens, auteurs-compositeurs, compositeurs, maisons de disques, éditeurs de musique, syndicats, corporations, sociétés de droits, organismes de gestion collective et tous les autres partis qui possèdent, contrôlent ou concédent les droits d’auteur, les effets sonores, l’audio et d’autres droits de propriété intellectuelle.

## <a name="call-agents"></a>Agents d’appel

Examinez les [conditions d’ajout des agents à une file d’attente ](plan-auto-attendant-call-queue.md#prerequisites).

![Capture d’écran des paramètres des utilisateurs et des groupes pour les files d’attente d’appels.](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a>Canal Teams

Vous pouvez ajouter jusqu’à 200 agents via un canal Teams. Vous devez être membre de l’équipe, créateur ou propriétaire du canal pour ajouter un canal à la file d’attente.

Si vous voulez [utiliser un canal Teams pour gérer la file d’attente](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e), sélectionnez l’option **Sélectionner une équipe**, puis cliquez sur **Ajouter un canal**. Recherchez l’équipe à utiliser, sélectionnez-la, puis cliquez sur **Ajouter**. Sélectionnez le canal que vous souhaitez utiliser (seuls les canaux standard sont pris en charge), puis cliquez sur **Appliquer**. 

Les clients suivants sont pris en charge lors de l’utilisation d’un canal Teams pour les files d’attente d’appels : 

  - client Microsoft Teams Windows
  - Client Microsoft Teams pour Mac

> [!NOTE]
> Si vous utilisez cette option, l’opération de la file d’attente d’appels peut prendre jusqu’à 24 heures.

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
  - Téléphonie Microsoft Teams version 1449/1.0.94.2020051601 ou ultérieure
  
Les comptes Teams des agents doivent être définis sur le mode Teams uniquement. Les agents qui ne répondent pas aux exigences ne sont pas inclus dans la liste de routage des appels. Nous vous recommandons d’activer le mode conférence pour vos files d’attente des appels si tous vos agents utilisent des clients compatibles.

> [!NOTE]
> Le mode conférence n’est pas pris en charge si les appels téléphoniques sont acheminés vers la file d’attente à partir d’une passerelle de routage direct activée pour le routage basé sur l’emplacement.

> [!TIP]
> La définition du **mode conférence** **sur Activé** est le paramètre recommandé.

La **méthode de routage** détermine l’ordre dans lequel les agents reçoivent les appels de la file d’attente. Sélectionnez l’une des options suivantes :

- Le **routage du standard** appelle tous les agents de la file d’attente en même temps. Le premier agent à prendre l’appel reçoit l’appel.

- Le **routage en série** appelle tous les agents d’appel les uns après les autres, dans l’ordre spécifié dans la liste des **Agents d’appel**. Si un agent ignore ou ne récupère pas un appel, l’appel sonnera l’agent suivant. Cette opération se répète jusqu’à ce que l’appel soit récupéré ou expiré.

- Le **tourniquet (round robin)** équilibre le routage des appels entrants afin que chaque agent d’appel reçoive le même nombre d’appels provenant de la file d’attente. Cette méthode de routage peut être souhaitable dans un environnement de vente entrant pour garantir l’égalité des chances entre tous les agents d’appel.

- L’**inactivité la plus longue** achemine chaque appel vers l’agent qui a été inactif le plus longtemps. Un agent est considéré comme inactif si son état de présence est Disponible. Les agents dont l’état de présence n’est pas Disponible ne pourront pas recevoir d’appels tant qu’ils n’auront pas changé leur présence en Disponible. 

> [!TIP]
> Le paramètre recommandé consiste à définir la **méthode de routage** **sur round robin** ou **idle le plus** long.

> [!NOTE]
> Si [l’enregistrement de conformité](teams-recording-policy.md) est activé sur les agents, la combinaison du **mode Conférence** et du **routage du standard** n’est pas prise en charge. Si vous devez utiliser le **mode Conférence**, sélectionnez **Routage série**, **tourniquet (round robin**) ou **Inactif le plus long** comme **méthode de routage**. Si vous devez utiliser le **routage du standard**, définissez le **mode Conférence** sur **Désactivé**.
> 
> Lorsque vous utilisez **l’inactivité la plus longue** et qu’il y a moins d’appels en file d’attente que les agents disponibles, seuls les deux premiers agents inactifs les plus longs sont présentés avec les appels de la file d’attente.
> 
> Lorsque vous utilisez **l’inactivité la plus longue** , il peut arriver qu’un agent reçoive un appel de la file d’attente peu après son indisponibilité ou s’il y a un court délai pour recevoir un appel de la file d’attente après être devenu disponible.
> 
> La présentation des appels de file d’attente d’appels aux agents peut entrer en conflit avec les restrictions de routage basé sur l’emplacement. Dans ce cas, l’agent reçoit un toast d’appel, mais ne peut pas répondre à l’appel. Cette condition se poursuit jusqu’à ce qu’un autre agent soit disponible pour répondre à l’appel, que l’appelant raccroche ou que la condition de délai d’expiration de la file d’attente d’appel se produise.  


![Capture d’écran des paramètres de routage, de désactivation et d’heure d’alerte.](media/call-queue-presence-agents-time.png)

Le **routage basé sur la présence** utilise le statut de disponibilité des agents d’appel pour déterminer si un agent doit être inclus dans la liste de routage des appels pour la méthode de routage sélectionnée. Les agents d’appel dont le statut de disponibilité est défini sur **Disponible** sont inclus dans la liste de routage des appels et peuvent recevoir des appels. Les agents dont le statut de disponibilité est défini sur un autre statut sont exclus de la liste de routage des appels et ne recevront pas d’appels tant que leur statut de disponibilité ne sera pas défini sur **Disponible**. 

Vous pouvez activer le routage des appels basé sur la présence avec toutes les méthodes de routage.

Si un agent refuse de recevoir des appels, il ne sera pas inclus dans la liste de routage des appels, quel que soit son statut de disponibilité. 

> [!NOTE]
> Lorsque **l’inactivité la plus longue** est sélectionnée comme méthode de routage, le routage basé sur la présence est requis et automatiquement activé, même si le bouton bascule de routage basé sur la présence est **désactivé** et grisé.
>
> Si le routage basé sur la présence n’est pas activé et qu’il y a plusieurs appels dans la file d’attente, le système présentera ces appels simultanément aux agents, quel que soit leur statut de présence. Cela entraînera plusieurs notifications d’appels aux agents, en particulier si certains agents ne répondent pas à l’appel initial qui leur est présenté.
> 
> Les agents qui utilisent le client Skype Entreprise ne sont pas inclus dans la liste de routage des appels lorsque le routage basé sur la présence est activé. Si certains de vos agents utilisent Skype Entreprise, n’activez pas le routage des appels basé sur la présence.

> [!TIP]
> La définition du **routage basé sur** présence sur **Activé** est le paramètre recommandé.

La **durée de l’alerte pour un agent** spécifie la durée pendant laquelle le téléphone d’un agent sonnera avant que la file d’attente ne redirige l’appel vers l’agent suivant.

> [!TIP]
> La définition de **l’heure d’alerte de l’agent** sur **20 secondes** est le paramètre recommandé.

## <a name="call-overflow-handling"></a>Gestion du débordement des appels

![Capture d’écran des paramètres de dépassement d’appel.](media/call-queue-overflow-handling.png)

Le **nombre maximal d’appels dans la file d’attente** spécifie le nombre maximal d’appels pouvant attendre dans la file d’attente à tout moment. La valeur par défaut est de 50, mais elle peut être définie sur une valeur comprise entre 0 et 200. Lorsque cette limite est atteinte, l’appel est géré comme cela est indiqué par le paramètre **Lorsque le nombre maximum d’appels est atteint**.

Vous pouvez choisir de mettre fin à l’appel ou de le rediriger vers l’une des destinations de routage des appels. Par exemple, vous pouvez demander à l’appelant de laisser un message vocal pour les agents dans la file d’attente. Pour les transferts externes, consultez [Les prérequis](plan-auto-attendant-call-queue.md#prerequisites) et les [transferts de numéros de téléphone externes . Détails techniques](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) de la mise en forme des numéros.

> [!NOTE]
> Si le nombre maximum d’appels est défini sur 0, le message d’accueil ne sera pas diffusé.

## <a name="call-timeout-handling"></a>Gestion de la temporisation des appels

![Capture d’écran des paramètres de délai d’expiration des appels.](media/call-queue-timeout-handling.png)

**Temporisation de l’appel : temps d’attente maximum** spécifie la durée maximum pendant laquelle un appel peut être mis en attente dans la file d’attente avant de le rediriger ou d’y mettre fin. Vous pouvez spécifier une valeur comprise entre 0 seconde et 45 minutes.

Vous pouvez choisir de mettre fin à l’appel ou de le rediriger vers l’une des destinations de routage des appels. Par exemple, vous pouvez demander à l’appelant de laisser un message vocal pour les agents dans la file d’attente. Pour les transferts externes, [reportez-vous aux prérequis](plan-auto-attendant-call-queue.md#prerequisites) et aux [transferts de numéros de téléphone externes : détails techniques](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) de la mise en forme des numéros.

Lorsque vous avez sélectionné vos options de temporisation des appels, cliquez sur **Enregistrer**.

## <a name="summary-of-recommended-call-queue-settings"></a>Résumé des paramètres de file d’attente d’appels recommandés

Les configurations ci-dessous sont recommandées :

- **Mode conférence** **activé**
- **Méthode de routage** sur **Tourniquet (round robin)** ou **Inactivité la plus longue**
- **Routage basé sur la présence** sur **Activé**
- **Durée de l’alerte pour un agent :** sur **20 secondes**


## <a name="call-queue-feature-compatibility"></a>Compatibilité des fonctionnalités de file d’attente d’appels

|Fonctionnalité                          |Teams <sup>Desktop1</sup> |Teams <sup>Mobile2</sup> |Lync |Téléphones IP | Files d’attente d’appels standard |Files d’attente d’appels basées sur un canal | Commentaire |
|:--------------------------------|:------------------------:|:-----------------------:|:---:|:--------:|:--------------------:|:------------------------:|:-------------|
|**Méthodes de routage de l’agent**        |                          |                         |     |          |                      |                          |              |
|`Attendant Routing`              |O                         |O                        |O    |O         |O                     |O                         |*Par défaut*     |
|`Longest Idle`<sup>3</sup>       |O                         |v                        |N    |O         |O                     |v                         |*Recommandé* |
|`Round Robin`                    |O                         |O                        |O    |O         |O                     |O                         |*Recommandé* |
|`Serial`                         |O                         |O                        |O    |v         |<sup>Y4</sup>         |<sup>Y4</sup>             |              |
|**Modes de transfert**               |                          |                         |     |          |                      |                          |              |
|`Conference Mode`<sup>5</sup>    |O                         |v                        |N    |<sup>Y6</sup>|O                  |O                         |*Recommandé* |
|`Transfer Mode`                  |O                         |O                        |O    |O         |O                     |v                         |              |
|Routage basé sur la <sup>présence3</sup>|O                        |v                        |N    |O         |O                     |v                         |*Recommandé* |
|Les agents peuvent refuser               |O                         |O                        |<sup>Y7</sup>|<sup>Y7</sup>|O          |O                         |*Par défaut*     |
|Files d’attente basées sur un canal             |v                         |N                        |N    |N         |n/a                   |<sup>Y8</sup>             |              |
|Le toast d’appel affiche le nom du compte de ressource |<sup>Y9</sup>       |O                        |O    |          |O                     |v                         |              |
|**ID d’appelant dynamique**            |                          |                         |     |          |                      |                          |              |
|`Standard call queue`            |N                         |O                        |N    |N         |O                     |n/a                       |              |
|`Channel based call queue`       |v                         |n/a                      |n/a  |n/a       |n/a                   |O                         |              |
|**Méthodes de connectivité RTC**    |                          |                         |     |          |                      |                          |Voir la note 10   |
|`Calling Plans`                  |O                         |O                        |O    |O         |O                     |O                         |              |
|`Direct Routing`                 |O                         |v                        |N    |N         |O                     |O                         |              |
|`Operator Connect`               |O                         |O                        |     |          |O                     |v                         |              |

Remarques :
1. Microsoft Teams Windows client, Microsoft Teams client Mac, Microsoft Teams sur l’infrastructure de bureau virtualisée, Microsoft Teams client web.
2. application Microsoft Teams iPhone, Microsoft Teams application Android.
3. La sélection de l’inactivité la plus longue pour la méthode de routage de l’agent active automatiquement le routage basé sur présence.
4. Peut uniquement définir l’ordre lors de l’ajout d’utilisateurs individuels dans le cadre de files d’attente d’appels standard. Lorsqu’une liste de distribution ou un canal Teams est utilisé, l’ordre est alphabétique.
5. Le mode conférence n’est pas pris en charge si les appels téléphoniques sont acheminés vers la file d’attente à partir d’une passerelle de routage direct activée pour le routage basé sur l’emplacement.
6. Microsoft Teams téléphone uniquement.
7. Via la page Portail Paramètres utilisateur à l’adressehttps://aka.ms/vmsettings
8. Seuls les canaux publics sont pris en charge.
9. Exclusion de Teams client Web.
10. Les standards automatiques et les files d’attente d’appels ne peuvent pas transférer d’appels entre des méthodes de connectivité RTC.


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
  - Microsoft Teams sur [Virtualized Desktop Infrastructure](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix et VMware)
  - Application Microsoft Teams pour iPhone
  - Application Microsoft Teams pour Android

    > [!NOTE]
    > Les files d’attente des appels auxquelles un numéro de routage direct est attribué ne prennent pas en charge les clients Skype Entreprise, les clients Lync ou les téléphones IP Skype Entreprise en tant qu’agents. Le client Teams est uniquement pris en charge avec un [mode de coexistence de Teams uniquement](/microsoftteams/setting-your-coexistence-and-upgrade-settings).

## <a name="call-queue-cmdlets"></a>Cmdlets de files d’attente des appels

Windows PowerShell vous permet de créer et de gérer des files d’attente d’appels via la ligne de commande par lot ou par programmation.

Les applets de commande suivantes vous permettent de gérer une file d’attente d’appels :

- [New-CsCallQueue](/powershell/module/skype/New-CsCallQueue)
- [Get-CsCallQueue](/powershell/module/skype/Get-CsCallQueue)
- [Set-CsCallQueue](/powershell/module/skype/Set-CsCallQueue)
- [Remove-CsCallQueue](/powershell/module/skype/Remove-CsCallQueue)

Les applets de commande supplémentaires suivantes sont également nécessaires pour gérer les utilisateurs, les comptes de ressources, les licences Téléphonie Microsoft Teams, les numéros de téléphone, les fichiers audio et le langage pris en charge qui seront utilisés avec les files d’attente d’appels :

Utilisateurs/Teams

- Utilisateurs
- - [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser)

- Teams : 
- - [Get-Team](/powershell/module/teams/Get-Team)
- - [Get-TeamChannel](/powershell/module/teams/Get-TeamChannel)

Comptes de ressources :

- [New-CsOnlineApplicationInstance](/powershell/module/skype/New-CsOnlineApplicationInstance)
- [Find-CsOnlineApplicationInstance](/powershell/module/skype/Find-CsOnlineApplicationInstance)
- [Get-CsOnlineApplicationInstance](/powershell/module/skype/Get-CsOnlineApplicationInstance)
- [Set-CsOnlineApplicationInstance](/powershell/module/skype/Set-CsOnlineApplicationInstance)
- [New-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/New-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociation)
- [Remove-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Remove-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociationStatus](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociationStatus)

Licences Teams Téléphone virtuelles :

- [Get-MsolAccountSku](/powershell/module/msonline/get-msolaccountsku)
- [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense)

Téléphone affectation de nombres :

- [Get-CsOnlineTelephoneNumber](/powershell/module/skype/Get-CsOnlineTelephoneNumber)
- [Set-CsPhoneNumberAssignment](/powershell/module/teams/Set-csphonenumberassignment)

Fichiers audio

- [Get-CsOnlineAudioFile](/powershell/module/skype/Get-CsOnlineAudioFile)
- [Import-CsOnlineAudioFile](/powershell/module/skype/Import-CsOnlineAudioFile)
- [Export-CsOnlineAudioFile](/powershell/module/skype/Export-CsOnlineAudioFile)
- [Remove-CsOnlineAudioFile](/powershell/module/skype/Remove-CsOnlineAudioFile)

Listes de langues de support

- [Get-CsAutoAttendantSupportedLanguage](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)

Pour obtenir un guide pas à pas sur la création de files d’attente d’appels avec PowerShell, consultez [Création de files d’attente d’appels avec des applets de commande PowerShell](create-a-phone-system-call-queue-via-cmdlets.md)

## <a name="call-queue-diagnostic-tool"></a>Outil de diagnostic de file d’attente d’appels

Si vous êtes administrateur, vous pouvez utiliser l’outil de diagnostic suivant pour vérifier qu’une file d’attente d’appels peut recevoir des appels :

1. Sélectionnez **Exécuter les tests** ci-dessous, qui remplira le diagnostic dans le Centre d'Administration Microsoft 365. 

   > [!div class="nextstepaction"]
   > [Exécuter des tests : file d’attente d’appels Teams](https://aka.ms/TeamsCallQueueDiag)

2. Dans le volet Exécuter le diagnostic, entrez le compte de ressource dans le champ **Nom d’utilisateur ou e-mail** , puis sélectionnez **Exécuter les tests**.

3. Les tests retournent les meilleures étapes suivantes pour traiter les configurations de locataire, de stratégie et de compte de ressource pour vérifier que la file d’attente d’appels est en mesure de recevoir des appels.

## <a name="related-topics"></a>Rubriques connexes

[Voici ce que vous obtenez avec Téléphonie Microsoft Teams](here-s-what-you-get-with-phone-system.md)

[Obtenir des numéros de téléphone de service](getting-service-phone-numbers.md)

[Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
