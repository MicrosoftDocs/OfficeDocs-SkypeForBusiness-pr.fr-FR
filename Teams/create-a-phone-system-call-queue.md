---
title: Créer une file d’attente des appels dans Microsoft Teams
author: DaniEASmith
ms.author: danismith
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
- highpri
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
description: Configurez des files d’attente d’appels dans Microsoft Teams. Les files d’attente d’appels fournissent un message d’accueil, contiennent de la musique, la redirection des appels et d’autres fonctionnalités.
ms.openlocfilehash: 8f997c36d8b1103e9f811bcff750749367c6f492
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242298"
---
# <a name="create-a-call-queue-in-microsoft-teams"></a>Créer une file d’attente des appels dans Microsoft Teams

Les files d’attente d’appels acheminent les appelants vers des personnes de votre organisation qui peuvent vous aider à résoudre un problème ou une question particulier. Les appels sont distribués un par un aux personnes de la file d’attente, appelées *agents*.

Les files d’attente des appels fournissent :

- un message d’accueil.
- une musique pour les personnes en attente dans la file d’attente.
- un routage des appels vers les agents, en utilisant la méthode *Premier entré, premier sorti* (PEPS).
- Gestion des options pour le débordement et la temporisation des files d’attente.

Avant de suivre les procédures décrites dans cet article, assurez-vous d’avoir lu [Planifier les standards automatiques teams et les files d’attente d’appels](plan-auto-attendant-call-queue.md) et suivi les [étapes de prise en main](plan-auto-attendant-call-queue.md#getting-started).

## <a name="whats-new-for-call-queues-in-the-past-six-months"></a>Nouveautés des files d’attente d’appels au cours des six derniers mois

- Août
  - **L’ajout d’un message d’accueil** (synthèse vocale (TTS)) est désormais pris en charge pour le message d’accueil principal de la file d’attente des appels.
  - Ignorer les contrôles de **message du système de messagerie vocale** sont désormais exposés lors du routage vers la messagerie vocale partagée, ce qui s’applique également aux invites **Ajouter un message d’accueil**.

## <a name="steps-to-create-a-call-queue"></a>Étapes de création d’une file d’attente d’appels

Les étapes de configuration d’une file d’attente d’appels sont les suivantes :

1. Configurer des informations générales
1. Définir le message d’accueil et la musique
1. Configurer le répondage d’appel
1. Choisir et affecter des agents
1. Définir la gestion du dépassement de capacité d’appel
1. Définir la gestion du délai d’expiration des appels

Les étapes décrites dans l’article créent des files d’attente d’appels à l’aide du Centre d’administration Teams. Pour obtenir des instructions sur la création de files d’attente d’appels à l’aide de PowerShell, consultez [Création de files d’attente d’appels avec des applets de commande PowerShell](create-a-phone-system-call-queue-via-cmdlets.md).

## <a name="follow-these-steps-to-set-up-your-call-queue"></a>Suivez ces étapes pour configurer votre file d’attente d’appels

# <a name="step-1-general-info"></a>[Étape 1 : Informations générales](#tab/general-info)

## <a name="step-1-set-up-general-information"></a>Étape 1 : Configurer les informations générales

Pour configurer une file d’attente d’appels, dans le [Centre d’administration Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851), développez **Voix**, sélectionnez **Files d’attente d’appels**, puis **Ajouter**.

Tapez un nom pour la file d’attente des appels dans la zone située en haut.

### <a name="add-a-resource-account"></a>Ajouter un compte de ressource

Pour ajouter un compte de ressource existant :

1. Sous **Comptes de ressources**, cliquez sur le bouton **Ajouter** pour ajouter un compte de ressource pour cette file d’attente d’appels.
1. Dans le volet **Ajouter des comptes** , recherchez le compte de ressource à ajouter.
1. Sélectionnez le bouton **Ajouter** en regard du compte de ressource que vous souhaitez affecter à cette file d’attente d’appels.
1. En bas du volet, sélectionnez le bouton **Ajouter** .

Si vous devez créer un compte de ressource :

1. Sous **Comptes de ressources**, cliquez sur le bouton **Ajouter** pour ajouter un compte de ressource pour cette file d’attente d’appels.
1. Dans le volet **Ajouter des comptes** , recherchez n’importe quel ensemble de lettres pour extraire la liste déroulante des résultats.
1. Sélectionnez le bouton **+ Ajouter un compte de ressource** en bas des résultats.
1. Dans le volet **Ajouter un compte de ressource** :
    1. Tapez un **nom d’affichage** descriptif, qui sera visible par les agents.
    1. Tapez un **nom d’utilisateur** descriptif pour le compte de ressource.
    1. Sélectionnez la liste déroulante **Type de compte** de ressource, puis sélectionnez **File d’attente d’appels**.
1. En bas du volet, sélectionnez le bouton **Enregistrer** .
1. Dans le volet **Comptes de ressources** , sélectionnez le bouton **Ajouter** .

Les agents voient le nom du compte de ressource lorsqu’ils reçoivent un appel entrant.

Pour plus d’informations, consultez [Gérer les comptes de ressources Teams](manage-resource-accounts.md).

### <a name="assign-a-calling-id-optional"></a>Affecter un ID d’appel (facultatif)

**Disponible pour les utilisateurs de bureau de canal/d’appel collaboratif Teams et les utilisateurs de clients mobiles Teams avec des files d’attente d’appels standard.**

Vous pouvez attribuer des numéros d’identification d’appelant sortants pour les agents en spécifiant un ou plusieurs comptes de ressources avec un numéro de téléphone. Les agents peuvent sélectionner le numéro d’ID de l’appelant sortant à utiliser avec chaque appel sortant qu’ils effectuent. Dans l’application Appels, les agents peuvent utiliser leur numéro de file d’attente d’appels /standard automatique (AA) ou leur propre numéro de numérotation directe à l’entrée (DID).

> [!NOTE]
> Le compte de ressource utilisé à des fins d’appel d’ID doit avoir une licence **de compte de ressource Téléphonie Microsoft Teams** et l’une des autorisations suivantes :
>
> - Une licence de forfait d’appels et un numéro de téléphone attribué
> - Un numéro de téléphone Operator Connect attribué
> - Une stratégie de routage des voix en ligne (l’attribution de numéro de téléphone est facultative lors de l’utilisation du routage direct)

1. Sous **Attribuer un ID d’appel**, sélectionnez le bouton **Ajouter** .
1. Dans le volet **Ajouter des comptes** , recherchez le ou les comptes de ressources que vous souhaitez autoriser les agents à utiliser à des fins d’ID d’appelant sortant.
1. Sélectionnez le bouton **Ajouter** en regard du compte de ressource avec un numéro de téléphone attribué.
1. Sélectionnez le bouton **Ajouter** en bas du volet.

Si vous n’avez pas de compte de ressource avec un numéro de téléphone attribué :

1. Sous **Comptes de ressources**, cliquez sur le bouton **Ajouter** pour ajouter un compte de ressource.
1. Dans le volet **Ajouter des comptes** , recherchez n’importe quel ensemble de lettres pour extraire la liste déroulante des résultats.
1. Sélectionnez le bouton **+ Ajouter un compte de ressource** en bas des résultats.
1. Dans le volet **Ajouter un compte de ressource** :
    1. Tapez un **nom d’affichage** descriptif, qui sera visible pour appeler les destinataires.
    1. Tapez un **nom d’utilisateur** descriptif pour le compte de ressource.
    1. Sélectionnez la liste déroulante **Type de compte** de ressource, puis sélectionnez **File d’attente d’appels**.
1. En bas du volet, sélectionnez le bouton **Enregistrer** .
1. Dans le volet **Comptes de ressources** , sélectionnez le bouton **Ajouter** .

Une fois que vous avez créé ce nouveau compte de ressource pour l’ID d’appel, vous devez toujours :

- Attribuer une [licence de compte de ressource téléphonique Teams](manage-resource-accounts.md#assign-a-license)
- Attribuer une licence de forfait d’appels Microsoft, attribuer un numéro de téléphone Operator Connect ou affecter une stratégie de routage vocal en ligne pour le routage direct
- Affectez le [numéro de téléphone du service au compte de ressource](manage-resource-accounts.md#assign-a-service-number), si vous utilisez Microsoft forfait d’appels

### <a name="set-the-call-queue-language"></a>Définir la langue de la file d’attente des appels

Choisissez une [langue prise en charge](create-a-phone-system-call-queue-languages.md).

Cette langue sera utilisée pour les invites vocales générées par le système et la transcription de la messagerie vocale, si vous les activez.

Une fois que vous avez sélectionné une langue, sélectionnez le bouton **Suivant** en bas de la page **Ajouter une file d’attente d’appels** .

# <a name="step-2-greeting-and-music"></a>[Étape 2 : Salutation et musique](#tab/greeting-music)

## <a name="step-2-add-a-greeting-and-on-hold-music"></a>Étape 2 : Ajouter un message d’accueil et de la musique en attente

*Nouveau : **l’ajout d’un message d’accueil** (synthèse vocale (TTS)) est désormais pris en charge pour le message d’accueil principal de la file d’attente des appels.*

Spécifiez si vous souhaitez lire un *message d’accueil* aux appelants lorsqu’ils arrivent dans la file d’attente.

- Si vous sélectionnez **Lire un fichier audio**, vous devez charger un fichier MP3, WAV ou WMA contenant le message d’accueil que vous souhaitez lire. La taille maximale de l’enregistrement téléchargé est de 5 Mo.

- Si vous sélectionnez **Taper un message d’accueil**, le système lit le texte que vous tapez (jusqu’à 1 000 caractères) lorsque la file d’attente d’appels répond à un appel.

Teams fournit la musique par défaut aux appelants lorsqu’ils sont *en attente dans une file d’attente*.

- La musique par défaut fournie dans les files d’attente des appels Teams est exempte de toute redevance payable par votre organisation.
- Si vous souhaitez diffuser un fichier audio spécifique, choisissez **Lire un fichier audio** et téléchargez un fichier MP3, WAV ou WMA.

> [!NOTE]
> Vous êtes responsable de l’effacement et de la sécurisation de tous les droits et autorisations nécessaires pour utiliser tout fichier audio ou de musique avec votre Microsoft service Teams, ce qui peut inclure la propriété intellectuelle et d’autres droits sur toute musique, effets sonores, audio, marques, noms et autres contenus dans le fichier audio de tous les titulaires de droits pertinents, y compris les artistes,  acteurs, artistes interprètes, musiciens, auteurs-compositeurs, compositeurs, labels de disques, éditeurs de musique, syndicats, guildes, sociétés de droits, organisations de gestion collective et toute autre partie qui possède, contrôle ou licence les droits d’auteur, effets sonores, audio et autres droits de propriété intellectuelle de la musique.

Une fois que vous avez sélectionné un message d’accueil et de la musique en attente, sélectionnez le bouton **Suivant** en bas de la page **Ajouter une file d’attente d’appels** .

# <a name="step-3-call-answering"></a>[Étape 3 : Répondre aux appels](#tab/call-answering)

## <a name="step-3-set-up-who-will-answer-incoming-calls"></a>Étape 3 : Configurer qui répondra aux appels entrants

Examinez les [conditions d’ajout des agents à une file d’attente ](plan-auto-attendant-call-queue.md#prerequisites).

### <a name="teams-channel"></a>Canal Teams

Vous pouvez ajouter jusqu’à 200 agents via un canal Teams. Vous devez être membre de l’équipe ou du créateur ou du propriétaire du canal pour ajouter un canal à la file d’attente.

Si vous souhaitez [utiliser un canal Teams pour gérer la file d’attente](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e) :

1. Sélectionnez la case d’option **Choisir une équipe** , puis **sélectionnez Ajouter un canal**.
1. Recherchez l’équipe que vous souhaitez utiliser, sélectionnez-la, puis **sélectionnez Ajouter**.
1. Sélectionnez le canal que vous souhaitez utiliser (seuls les canaux standard sont pris en charge), puis sélectionnez **Appliquer**.

Les clients suivants sont pris en charge lors de l’utilisation d’un canal Teams pour les files d’attente d’appels :

- Microsoft client Windows Teams
- Client Microsoft Teams pour Mac

> [!NOTE]
> Si vous utilisez cette option, le fonctionnement complet de la file d’attente des appels peut prendre jusqu’à 24 heures.
>
> S’il y a plus de 200 membres dans l’équipe, seuls les 200 premiers membres, par ordre alphabétique, sont ajoutés en tant qu’agents à la file d’attente des appels.

### <a name="users-and-groups"></a>Utilisateurs et groupes

Vous pouvez ajouter jusqu’à 20 agents individuellement et jusqu’à 200 agents via des groupes.

Si vous souhaitez ajouter des utilisateurs ou des groupes individuels à la file d’attente :

1. Sélectionnez la case d’option **Choisir des utilisateurs et des groupes** .

Pour **ajouter un utilisateur** à la file d’attente :

1. Sélectionnez **Ajouter des utilisateurs**, recherchez l’utilisateur, cliquez sur **Ajouter**, puis sur **Ajouter**.

Pour **ajouter un groupe** à la file d’attente :

1. Sélectionnez **Ajouter des groupes**, recherchez le groupe, cliquez sur **Ajouter**, puis sur **Ajouter**. 
    1. Vous pouvez utiliser des listes de distribution, des groupes de sécurité et des groupes Microsoft 365 ou des équipes Microsoft Teams.

> [!NOTE]
> L’arrivée du premier appel peut prendre jusqu’à huit heures pour les nouveaux utilisateurs ajoutés à un groupe.
>
> S’il y a plus de 200 membres dans le groupe, seuls les 200 premiers membres, par ordre alphabétique, sont ajoutés en tant qu’agents à la file d’attente des appels.

### <a name="conference-mode"></a>Conference mode (Mode Conférence)

**Le mode conférence** réduit le temps nécessaire à la connexion d’un appelant à un agent après l’acceptation de l’appel. Pour que le mode conférence fonctionne, les agents de la file d’attente des appels doivent utiliser l’un des clients suivants :

- la dernière version du client Microsoft Teams pour ordinateur de bureau, de l’application Android ou de l’application iOS
- Téléphonie Microsoft Teams version 1449/1.0.94.2020051601 ou ultérieure
  
Les comptes Teams des agents doivent être définis sur le mode TeamsOnly. Les agents qui ne répondent pas aux exigences ne sont pas inclus dans la liste de routage des appels. Nous vous recommandons d’activer le mode conférence pour vos files d’attente d’appels si vos agents utilisent des clients compatibles.

> [!TIP]
> Le **paramètre** recommandé est de définir mode conférence sur **Activé** .

> [!NOTE]
> Le mode conférence n’est pas pris en charge si les appels téléphoniques sont routés vers la file d’attente à partir d’une passerelle de routage direct activée pour le routage basé sur l’emplacement.
>
> Le mode conférence n’est pas pris en charge si les appels téléphoniques sont routés vers la file d’attente à partir de Skype Entreprise Server.
> 
> Le mode conférence est requis si les utilisateurs de Teams doivent consulter/transférer des appels avec des files d’attente d’appels.
>
> Les agents peuvent entendre la musique configurée en attente dans la file d’attente pendant jusqu’à 2 secondes lors de la première jointure de l’appel.
> 
> Si [l’enregistrement de conformité](teams-recording-policy.md) est activé sur les agents, la combinaison du mode conférence et du routage Attendant n’est pas prise en charge. Si vous avez besoin d’utiliser le mode Conférence, sélectionnez **Routage série**, **Tourniquet** **Inactif le plus long** comme **méthode de routage**. Si vous avez besoin d’utiliser le routage Attendant, définissez mode de conférence sur **Désactivé**.

Une fois que vous avez sélectionné vos options de réponse aux appels, sélectionnez le bouton **Suivant** en bas de la page **Ajouter une file d’attente d’appels** .

# <a name="step-4-agent-selection"></a>[Étape 4 : Sélection de l’agent](#tab/agent-selection)

## <a name="step-4-select-your-agent-routing-options"></a>Étape 4 : Sélectionner les options de routage de votre agent

La **méthode de routage** détermine l’ordre dans lequel les agents reçoivent les appels de la file d’attente.

Sélectionnez l’une des options suivantes :

- Le **routage du standard** appelle tous les agents de la file d’attente en même temps. Le premier agent à prendre l’appel reçoit l’appel.

- Le **routage en série** appelle tous les agents d’appel les uns après les autres, dans l’ordre spécifié dans la liste des **Agents d’appel**. Si un agent ignore ou ne décroche pas un appel, l’appel sonne l’agent suivant. Cette opération se répète jusqu’à ce que l’appel soit récupéré ou expire.

- Le **tourniquet (round robin)** équilibre le routage des appels entrants afin que chaque agent d’appel reçoive le même nombre d’appels provenant de la file d’attente. Cette méthode de routage peut être souhaitable dans un environnement de vente entrante pour garantir l’égalité des chances entre tous les agents d’appel.

- L’**inactivité la plus longue** achemine chaque appel vers l’agent qui a été inactif le plus longtemps. Un agent est considéré comme inactif si son état de présence est Disponible. Les agents dont l’état de présence n’est pas Disponible ne seront pas éligibles pour recevoir des appels tant qu’ils ne changeront pas leur présence sur Disponible.

> [!TIP]
> Définir la **méthode de routage** sur **Tourniquet** **le plus long inactif** est le paramètre recommandé.

> [!NOTE]
> Si [l’enregistrement de conformité](teams-recording-policy.md) est activé sur les agents, la combinaison du **mode conférence** et **du routage Attendant** n’est pas prise en charge. Si vous avez besoin d’utiliser le **mode Conférence**, sélectionnez **Routage série**, **Tourniquet** **Inactif le plus long** comme **méthode de routage**. Si vous avez besoin d’utiliser le **routage Attendant**, définissez **mode de conférence** sur **Désactivé**.
>
> Lorsque vous utilisez **la durée d’inactivité la plus longue** et qu’il y a moins d’appels dans la file d’attente que les agents disponibles, seuls les deux agents inactifs les plus longs sont présentés avec des appels à partir de la file d’attente.
>
> Lors de l’utilisation **de La plus longue inactivité**, il peut arriver qu’un agent reçoive un appel de la file d’attente peu de temps après qu’il est devenu indisponible, ou qu’un court retard dans la réception d’un appel de la file d’attente après être devenu disponible.
>
> La présentation des appels de file d’attente aux agents peut entrer en conflit avec les restrictions de routage basée sur l’emplacement. Dans ce cas, l’agent recevra un toast d’appel, mais ne pourra pas répondre à l’appel. Cette condition se poursuit jusqu’à ce qu’un autre agent soit disponible pour répondre à l’appel, que l’appelant raccroche ou que la condition de délai d’attente des appels se produise.  

### <a name="presence-based-call-routing"></a>Routage des appels basé sur la présence

**Le routage des appels basé sur la présence** utilise l’état de disponibilité des agents d’appel pour déterminer si un agent doit être inclus dans la liste de routage des appels pour la méthode de routage sélectionnée.

Les agents d’appel dont le statut de disponibilité est défini sur **Disponible** sont inclus dans la liste de routage des appels et peuvent recevoir des appels. Les agents dont le statut de disponibilité est défini sur un autre statut sont exclus de la liste de routage des appels et ne recevront pas d’appels tant que leur statut de disponibilité ne sera pas défini sur **Disponible**.

Vous pouvez activer le **routage des appels basé sur la présence** avec l’une des méthodes de routage.

Si un agent refuse de recevoir des appels, il ne sera pas inclus dans la liste de routage des appels, quel que soit son statut de disponibilité.

> [!TIP]
> Le paramètre recommandé est de définir le **routage basé sur la présence** **sur activé** .

> [!NOTE]
> Lorsque la méthode de routage **La plus longue inactivité** est sélectionnée, le routage basé sur la présence est requis et automatiquement activé, même si le bouton bascule de routage basé sur la présence est **Désactivé** et grisé.
>
> Si le routage basé sur la présence n’est pas activé et qu’il y a plusieurs appels dans la file d’attente, le système présente ces appels simultanément aux agents, quel que soit leur statut de présence. Cette action entraîne plusieurs notifications d’appel aux agents, en particulier si certains agents ne répondent pas à l’appel initial qui leur est présenté.
>
> Lors de l’utilisation du **routage basé sur la présence**, il peut arriver qu’un agent reçoive un appel de la file d’attente peu de temps après être devenu indisponible ou qu’un court délai pour recevoir un appel de la file d’attente après être devenu disponible.
>
> Les agents qui utilisent le client Skype Entreprise ne sont pas inclus dans la liste de routage des appels lorsque le routage basé sur la présence est activé. Si certains de vos agents utilisent Skype Entreprise, n’activez pas le routage des appels basé sur la présence.

### <a name="call-agents-can-opt-out-of-taking-calls"></a>Les agents d’appel peuvent refuser de passer des appels

Vous pouvez spécifier si les agents d’appel ont la possibilité de refuser la prise d’appels ou non.

Nous vous recommandons d’activer **l’option Les agents d’appel peuvent refuser de passer des appels**.

### <a name="agent-alert-time"></a>Heure de l’alerte de l’agent

La **durée de l’alerte pour un agent** spécifie la durée pendant laquelle le téléphone d’un agent sonnera avant que la file d’attente ne redirige l’appel vers l’agent suivant.

> [!TIP]
> Le paramètre recommandé est de définir **l’heure d’alerte de l’agent** sur **un minimum de 20 secondes** .

Une fois que vous avez sélectionné les options de routage des appels de votre agent, sélectionnez le bouton **Suivant** en bas de la page **Ajouter une file d’attente d’appels** .

# <a name="step-5-call-overflow"></a>[Étape 5 : Dépassement de capacité des appels](#tab/call-overflow)

## <a name="step-5-set-how-to-handle-call-overflow"></a>Étape 5 : Définir comment gérer le dépassement de capacité d’appel

Le **nombre maximal d’appels dans la file d’attente** spécifie le nombre maximal d’appels pouvant attendre dans la file d’attente à tout moment.

La valeur par défaut est de 50, mais elle peut être définie sur une valeur comprise entre 0 et 200.

Lorsque cette limite est atteinte, l’appel est géré comme cela est indiqué par le paramètre **Lorsque le nombre maximum d’appels est atteint**.

Vous pouvez choisir de **déconnecter** l’appel ou de le **rediriger vers** l’une des destinations de routage des appels.

Par exemple, vous pouvez demander à l’appelant de laisser un message vocal pour les agents dans la file d’attente.

*Nouveau : ignorer les contrôles de **message du système de messagerie vocale** sont désormais exposés lors du routage vers la messagerie vocale partagée, ce qui s’applique également aux invites **Ajouter un message d’accueil** .*

Pour les transferts externes, consultez [Prérequis](./plan-auto-attendant-call-queue.md#prerequisites) et [transferts de numéros de téléphone externes - Détails techniques](create-a-phone-system-auto-attendant.md?tabs=additional-resources) pour la mise en forme des numéros.

> [!NOTE]
> Si le nombre maximal d’appels est défini sur 0, le message d’accueil ne sera pas lu.
>  
> La messagerie vocale (personnelle) envoie des appels à l’utilisateur et non directement à sa messagerie vocale comme indiqué. Ce problème fait l’objet d’une enquête du support technique.

Une fois que vous avez sélectionné vos options de gestion du dépassement de capacité d’appel, sélectionnez le bouton **Suivant** en bas de la page **Ajouter une file d’attente d’appels** .

# <a name="step-6-call-timeout"></a>[Étape 6 : Délai d’expiration des appels](#tab/call-timeout)

## <a name="step-6-set-how-to-handle-call-timeouts"></a>Étape 6 : Définir comment gérer les délais d’expiration des appels

**Temporisation de l’appel : temps d’attente maximum** spécifie la durée maximum pendant laquelle un appel peut être mis en attente dans la file d’attente avant de le rediriger ou d’y mettre fin.

Vous pouvez spécifier une valeur comprise entre 0 seconde et 45 minutes.

Vous pouvez choisir de **déconnecter** l’appel ou de le **rediriger vers** l’une des destinations de routage des appels.

Par exemple, vous pouvez demander à l’appelant de laisser un message vocal pour les agents dans la file d’attente.

*Nouveau : ignorer les contrôles de **message du système de messagerie vocale** sont désormais exposés lors du routage vers la messagerie vocale partagée, ce qui s’applique également aux invites **Ajouter un message d’accueil** .*

Pour les transferts externes, consultez [Prérequis](./plan-auto-attendant-call-queue.md#prerequisites) et [transferts de numéros de téléphone externes - Détails techniques](create-a-phone-system-auto-attendant.md?tabs=additional-resources) pour la mise en forme des numéros.

> [!NOTE]
> La messagerie vocale (personnelle) envoie des appels à l’utilisateur et non directement à sa messagerie vocale comme indiqué. Ce problème fait l’objet d’une enquête du support technique.

Une fois que vous avez sélectionné les options de gestion du délai d’expiration des appels, sélectionnez le bouton **Envoyer** en bas de la page **Ajouter une file d’attente d’appels** .

---

## <a name="resources-for-complex-scenarios"></a>Ressources pour les scénarios complexes

### <a name="summary-of-recommended-call-queue-settings"></a>Résumé des paramètres de file d’attente d’appels recommandés

Les configurations ci-dessous sont recommandées :

- **Mode conférence** sur **Activé**
- **Méthode de routage** sur **Tourniquet (round robin)** ou **Inactivité la plus longue**
- **Routage basé sur la présence** sur **Activé**
- **Durée de l’alerte de l’agent :** au minimum **20 secondes**

### <a name="call-queue-feature-compatibility"></a>Compatibilité des fonctionnalités de file d’attente d’appels

|Fonctionnalité                          |Teams Desktop<sup>1</sup> |Teams Web | Teams Mobile<sup>2</sup> |Skype Entreprise |Téléphones IP | Files d’attente d’appels standard |Files d’attente d’appels basées sur un canal | Commentaire |
|:--------------------------------|:------------------------:|:--------:|:--------------:|:---:|:--------:|:--------------------:|:------------------------:|:--------|
|**Méthodes de routage de l’agent**        |                          |          |                |     |          |                      |                          |   |
|`Attendant Routing`              |O                         |O         |O               |O    |O         |O                     |v                         |*Par défaut*     |
|`Longest Idle`<sup>3</sup>       |O                         |O         |v               |N    |O         |O                     |v                         |*Recommandé* |
|`Round Robin`                    |O                         |O         |O               |O    |O         |O                     |v                         |*Recommandé* |
|`Serial`                         |O                         |O         |O               |O    |v         |Y<sup>4</sup>         |Y<sup>4</sup>             |   |
|**Options de routage de l’agent**        |                          |          |                |     |          |                      |                          |   |
|`Presence Based Routing`<sup>3</sup>|O                      |O         |v               |N    |O         |O                     |v                         |*Par défaut* |
|`Agents can Opt-out`<sup>10</sup> |O                       |O         |O               |Y<sup>7</sup>|Y<sup>7</sup>|O          |v                         |*Par défaut*     |
|**Modes de transfert**               |                          |          |                |     |          |                      |                          |   |
|`Conference Mode`<sup>5</sup>    |O                         |O         |v               |N    |Y<sup>6</sup>|O                  |v                         |*Par défaut* |
|`Transfer Mode`                  |O                         |O         |O               |O    |O         |O                     |v                         |   |
|**Appel collaboratif**        |                          |          |                |     |          |                      |                          |   |
|`Channel Based Queues`             |v                       |N         |N               |N    |N         |n/a                   |Y<sup>8</sup>             |   |
|**ID d’appelant dynamique**            |                          |          |                |     |          |                      |                          |   |
|`Standard call queue`            |O                         |O         |v               |N    |N         |O                     |n/a                       |   |
|`Channel based call queue`       |v                         |n/a       |n/a             |n/a  |n/a       |n/a                   |v                         |   |
|**Méthodes de connectivité RTC**    |                          |          |                |     |          |                      |                          |Voir la note 9   |
|`Calling Plans`                  |O                         |O         |O               |O    |O         |O                     |O                         |   |
|`Direct Routing`                 |O                         |O         |v               |N    |O         |Y<sup>6</sup>         |O                         |   |
|`Operator Connect`               |O                         |O         |O               |     |v         |Y<sup>6</sup>         |v                         |   |
|**Divers**                |                          |          |                |     |          |                      |                          |   |
|`Call toast shows Resource Account Name` |v                 |N         |O               |O    |          |O                     |v                         |              |

#### <a name="notes"></a>Remarques

1. Microsoft client Windows Teams, Microsoft Client Mac Teams, Microsoft Teams sur l’infrastructure de bureau virtualisée.
2. Microsoft application Pour iPhone Teams, Microsoft l’application Android Teams.
3. La sélection de la méthode d’inactivité la plus longue pour la méthode de routage de l’agent active automatiquement le routage basé sur la présence.
4. Il n’est pas possible de définir l’ordre dans lequel les agents seront appelés.
5. Le mode conférence n’est pas pris en charge si les appels téléphoniques sont routés vers la file d’attente à partir d’une passerelle de routage direct activée pour le routage basé sur l’emplacement.
6. Téléphonie Microsoft Teams uniquement.
7. Via la page du portail paramètres utilisateur à l’adresse [https://aka.ms/vmsettings](https://aka.ms/vmsettings).
8. Seuls les canaux publics sont pris en charge.
9. Les standards automatiques et les files d’attente d’appels ne peuvent pas transférer les appels entre les méthodes de connectivité RTC.
10. Pour GCCH/DOD, disponible uniquement via le portail des paramètres utilisateur à l’adresse suivante :
- GCCH : [https://dialin.cpc.gov.teams.microsoft.us/usp](https://dialin.cpc.gov.teams.microsoft.us/usp)
- DOD: [https://dialin.cpc.dod.teams.microsoft.us/usp](https://dialin.cpc.dod.teams.microsoft.us/usp)

### <a name="supported-clients"></a>Clients pris en charge

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
- Microsoft Teams sur [l’infrastructure de bureau virtualisé](teams-for-vdi.md) (Windows Virtual Desktop, Citrix et VMware)
- Application Microsoft Teams pour iPhone
- Application Microsoft Teams pour Android

  > [!NOTE]
  > Les files d’attente des appels auxquelles un numéro de routage direct est attribué ne prennent pas en charge les clients Skype Entreprise, les clients Lync ou les téléphones IP Skype Entreprise en tant qu’agents. Le client Teams est uniquement pris en charge avec un [mode de coexistence Teams uniquement](setting-your-coexistence-and-upgrade-settings.md).

### <a name="call-queue-diagnostic-tool"></a>Outil de diagnostic de file d’attente des appels

Si vous êtes administrateur, vous pouvez utiliser l’outil de diagnostic suivant pour vérifier qu’une file d’attente d’appels peut recevoir des appels :

1. Sélectionnez **Exécuter les tests** ci-dessous, qui remplira le diagnostic dans le Centre d'Administration Microsoft 365.

   > [!div class="nextstepaction"]
   > [Exécuter des tests : File d’attente des appels Teams](https://aka.ms/TeamsCallQueueDiag)

2. Dans le volet Exécuter le diagnostic, entrez le compte de ressource dans le champ **Nom d’utilisateur ou Email**, puis sélectionnez **Exécuter les tests**.

3. Les tests retournent les meilleures étapes suivantes pour traiter les configurations de locataire, de stratégie et de compte de ressource afin de vérifier que la file d’attente des appels est en mesure de recevoir des appels.

### <a name="related-topics"></a>Rubriques connexes

[Voici ce que vous obtenez avec Téléphonie Microsoft Teams](here-s-what-you-get-with-phone-system.md)

[Obtenir des numéros de téléphone de service](getting-service-phone-numbers.md)

[Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
