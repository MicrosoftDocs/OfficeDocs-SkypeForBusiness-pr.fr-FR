---
title: Créer une file d’attente d’appels dans Microsoft Teams
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: Découvrez comment configurer phone system pour les files d’attente avec Microsoft Teams, qui fournit un message de salutation, de la musique, la redirection d’appels et d’autres fonctionnalités.
ms.openlocfilehash: 963633ef3ba1743522dbbacb93166f20d489e8be
ms.sourcegitcommit: d3883b3d9de7251e60033bece53a2bab17d7b1b8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/30/2021
ms.locfileid: "51450631"
---
# <a name="create-a-call-queue"></a>Créer une file d’attente d’appel

Les files d’attente permettent de router les appelants vers des personnes de votre organisation qui peuvent vous aider à répondre à un problème ou une question spécifique. Les appels sont distribués un par un aux personnes dans la file d’attente (appelées *agents).* 

Les files d’attente fournissent les services :

- Message de salutation.

- Musique pendant que des personnes patientent dans une file d’attente.

- Routage des appels *(dans l’ordre* Premier dans, Premier sorti (FIFO) - vers des agents.

- Options de gestion pour le dépassement de capacité et le délai d’attente.

Avant de suivre les procédures de cet article, [](plan-auto-attendant-call-queue.md#getting-started) assurez-vous de lire l’article Plan pour les standard [automatiques Teams](plan-auto-attendant-call-queue.md) et les files d’attente d’appels, et suivez les étapes de mise en place.

Pour configurer une file d’attente d’appels, dans le Centre d’administration Teams, développez **Voix,** cliquez sur Files d’attente d’appels, puis cliquez sur **Ajouter.**

## <a name="resource-account-and-language"></a>Compte et langue des ressources

![Capture d’écran des paramètres de compte de ressource et de langue](media/call-queue-name-language.png)

1. Tapez un nom pour la file d’attente d’appels.

2. Cliquez **sur Ajouter des comptes,** recherchez le compte de ressource à utiliser avec cette file d’attente d’appels, cliquez sur Ajouter, puis sur **Ajouter.**  (Les agents voient le nom du compte de ressource lorsqu’ils reçoivent un appel entrant.)

3. Choisissez une [langue prise en charge.](create-a-phone-system-call-queue-languages.md) Cette langue sera utilisée pour les invites vocales générées par le système et la transcription des messages vocaux (si vous les activez).

## <a name="greetings-and-music-on-hold-in-queue"></a>Salutations et musique en attente dans la file d’attente

Indiquez si vous souhaitez lire un message d’accueil pour les appelants lorsqu’ils arrivent dans la file d’attente. Vous devez charger un fichier MP3, WAV ou WMA contenant le message d’accueil à lire.

Teams fournit de la musique par défaut aux appelants lorsqu’ils sont en attente dans une file d’attente. Si vous souhaitez lire un fichier audio spécifique, sélectionnez Lire un fichier **audio** et téléchargez un fichier MP3, WAV ou WMA.

> [!NOTE]
> L’enregistrement téléchargé ne peut pas avoir une taille supérieure à 5 Mo.
> La musique par défaut fournie dans les files d’attente d’appels de Teams est gratuite pour toutes les redevances payables par votre organisation. 

## <a name="call-agents"></a>Appeler des agents

Examinez les conditions [préalables pour ajouter des agents à une file d’attente d’appels.](plan-auto-attendant-call-queue.md#prerequisites)

![Capture d’écran des paramètres d’utilisateurs et de groupes pour les files d’attente d’appels](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a>Canal Teams

Vous pouvez ajouter jusqu’à 200 agents via un canal Teams.

Si vous voulez utiliser [un canal Teams](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)pour gérer la file d’attente, sélectionnez l’option Choisir une équipe, puis cliquez sur Ajouter un **canal.**  Recherchez l’équipe que vous voulez utiliser, sélectionnez-la, puis cliquez **sur Ajouter.** Sélectionnez le canal que vous voulez utiliser, puis cliquez **sur Appliquer.**

##### <a name="users-and-groups"></a>Utilisateurs et groupes

Vous pouvez ajouter jusqu’à 20 agents individuellement et jusqu’à 200 agents par groupes.

Si vous voulez ajouter des utilisateurs individuels ou des groupes à la file d’attente, sélectionnez l’option Choisir des **utilisateurs et des** groupes. 

Pour ajouter un utilisateur à la file d’attente, cliquez sur Ajouter des utilisateurs, recherchez l’utilisateur, cliquez sur **Ajouter,** puis sur **Ajouter.**

Pour ajouter un groupe à la file d’attente, cliquez sur Ajouter des **groupes,** recherchez le groupe, cliquez sur **Ajouter,** puis sur **Ajouter.** Vous pouvez utiliser des listes de distribution, des groupes de sécurité et des groupes Microsoft 365 ou des équipes Microsoft Teams.

> [!NOTE]
> L’arrivée du premier appel peut prendre jusqu’à huit heures pour que les nouveaux utilisateurs ajoutés à un groupe arrivent.

## <a name="call-routing"></a>Routage des appels

![Capture d’écran des paramètres du mode de conférence et de la méthode de routage](media/call-queue-conference-mode-routing-method.png)

**Le mode conférence** réduit considérablement le temps qu’il faut pour qu’un appelant se connecte à un agent une fois qu’il accepte l’appel. Pour que le mode conférence fonctionne, les agents dans la file d’attente d’appels doivent utiliser l’un des clients suivants :

  - Dernière version du client de bureau Microsoft Teams, de l’application Android ou de l’application iOS
  - Microsoft Teams Phone version 1449/1.0.94.2020051601 ou version ultérieure
  
Les comptes Teams des agents doivent être réglés en mode Teams uniquement. Les agents qui ne répondent pas aux exigences ne figurent pas dans la liste de routage des appels. Nous vous recommandons d’activer le mode conférence pour vos files d’attente d’appels si vos agents utilisent tous des clients compatibles.

**La méthode de routage** détermine l’ordre dans lequel les agents reçoivent les appels de la file d’attente. Choisissez l’une des options ci-après :

- **Le routage d’Attendant** sonne tous les agents dans la file d’attente en même temps. Le premier appelant à prendre l’appel reçoit l’appel.

- **Le routage en série** sonne tous les télét calleurs un par un dans l’ordre spécifié dans la liste **Des télé appelants.** Si un agent le fait sans appel ou ne décroche pas, l’appel sonnera sur l’agent suivant et essaiera tous les agents jusqu’à ce qu’il soit choisi ou mis hors appel.

- **L’arrondi balance** le routage des appels entrants de sorte que chaque agent d’appel reçoie le même nombre d’appels depuis la file d’attente. Cela pourrait être souhaitable dans un environnement de vente entrante afin d’assurer la même opportunité entre tous les agents d’appel.

- **Les itinéraires inactifs** les plus longs à chaque appel à l’agent inactif la plus longue. Un agent est considéré comme inactif si son état de présence est disponible ou s’il est absent depuis moins de 10 minutes. Les agents dont l’état de présence est Absent depuis plus de 10 minutes ne sont pas considérés comme inactifs et ne peuvent pas recevoir d’appels tant qu’ils ne sont pas disponibles. 

![Capture d’écran des paramètres de routage, de désinspondage et d’heure d’alerte](media/call-queue-presence-agents-time.png)


**Le routage** basé sur la présence utilise le statut de disponibilité des agents d’appel pour déterminer si un agent doit être inclus dans la liste de routage des appels pour la méthode de routage sélectionnée. Les agents d’appel  dont le statut de disponibilité est Disponible sont inclus dans la liste de routage des appels et peuvent recevoir des appels. Les agents dont le statut de disponibilité est définie sur tout autre statut sont exclus de la liste de routage des appels et ne reçoivent pas d’appels jusqu’à ce que leur statut de disponibilité soit de nouveau **disponible.** 

Vous pouvez activer le routage des appels en fonction de la présence avec n’importe quelle méthode de routage.

Si un agent choisit de ne plus recevoir d’appels, il ne sera pas inclus dans la liste de routage des appels, quel que soit son statut de disponibilité. 

> [!NOTE]
> Les agents qui utilisent le client Skype Entreprise ne figurent pas dans la liste de routage des appels lorsque le routage en fonction de la présence est activé. Si des agents utilisent Skype Entreprise, n’activez pas le routage des appels en fonction de la présence.

**La durée d’alerte** de l’agent indique combien de temps le téléphone d’un agent sonnera avant que la file d’attente redirige l’appel vers le prochain agent.

Les paramètres suivants sont recommandés :

- **Mode conférence sur** **Automatique**
- **Méthode de routage vers** **le rond rond** ou le plus long **inactif**
- **Routage en fonction de la présence** vers **Le**
- **Heure d’alerte de l’agent :** **à 20 secondes**

> [!NOTE]
> Si le routage en fonction de la présence n’est pas activé et que la file d’attente compte plusieurs appels, le système les présente simultanément aux agents, quel que soit leur statut de présence. Cela entraîne plusieurs notifications d’appel pour les agents, particulièrement si certains agents ne répondent pas à l’appel initial qui leur est présenté.

## <a name="call-overflow-handling"></a>Gestion des débordements d’appels

![Capture d’écran des paramètres de dépassement de capacité d’appel](media/call-queue-overflow-handling.png)

**Le nombre maximal d’appels dans** la file d’attente indique le nombre maximal d’appels qui peuvent attendre dans la file d’attente à un moment donné. La valeur par défaut est 50, mais elle peut varier entre 0 et 200. Lorsque cette limite est atteinte, l’appel est traité comme spécifié par le paramètre Lorsque la limite maximale du nombre d’appels **est** atteinte.

Vous pouvez choisir de déconnecter l’appel ou de le rediriger vers une des destinations de routage des appels. Par exemple, l’appelant peut laisser un message vocal pour les agents dans la file d’attente. Pour les transferts externes, reportez-vous aux conditions [préalables](plan-auto-attendant-call-queue.md#prerequisites) et aux transferts de numéros de téléphone [externes ( détails techniques](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) pour la mise en forme des numéros).

> [!NOTE]
> Si la valeur maximale du nombre d’appels est définie sur 0, le message d’accueil n’est pas l donné.

## <a name="call-timeout-handling"></a>Traitement des délais d’appel

![Capture d’écran des paramètres de délai d’appel](media/call-queue-timeout-handling.png)

**Délai d’attente d’appel** : le temps d’attente maximal spécifie la durée maximale pendant quelle la file d’attente d’un appel peut être mis en attente avant d’être redirigé ou déconnecté. Vous pouvez spécifier une valeur de 0 seconde à 45 minutes.

Vous pouvez choisir de déconnecter l’appel ou de le rediriger vers l’une des destinations de routage des appels. Par exemple, l’appelant peut laisser un message vocal pour les agents dans la file d’attente. Pour les transferts externes, reportez-vous aux conditions [préalables](plan-auto-attendant-call-queue.md#prerequisites) et aux transferts de numéros de téléphone [externes - détails techniques](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) pour la mise en forme des numéros.

Une fois vos options de délai d’appel sélectionnées, cliquez sur **Enregistrer.**

## <a name="caller-id-for-outbound-calls"></a>ID de l’appelant pour les appels sortants

Étant donné que des agents dans une file d’attente d’appels peuvent appeler pour renvoyer un appel client, envisagez de définir l’ID d’appelant pour les membres d’une file d’attente d’appels sur le numéro de service d’un fournisseur de service automatique approprié. Pour plus d’informations, voir Gérer les [stratégies d’ID](caller-id-policies.md) d’appelant dans Microsoft Teams.

## <a name="supported-clients"></a>Clients pris en charge

Les clients suivants sont pris en charge pour les agents d’appel dans une file d’attente d’appels :

  - Client de bureau Skype Entreprise 2016 (versions 32 bits et 64 bits)
  - Client de bureau Lync 2013 (versions 32 bits et 64 bits)
  - Tous les modèles de téléphone IP pris en charge par Microsoft Teams. Consultez [Obtention de numéros de téléphone pour Skype Entreprise Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).
  - Mac Skype Entreprise Client (version 16.8.196 et ultérieures)
  - Client Skype Entreprise Pour Android (version 6.16.0.9 et ultérieures)
  - iPhone client Skype Entreprise (version 6.16.0 et ultérieures)
  - Client Skype Entreprise pour iPad (version 6.16.0 et ultérieures)
  - Client Windows Microsoft Teams (versions 32 bits et 64 bits)
  - Client Microsoft Teams Mac
  - Application Microsoft Teams pour iPhone
  - Application Microsoft Teams pour Android

    > [!NOTE]
    > Les files d’attente à qui un numéro de routage direct est attribué ne peuvent pas être prise en charge par les clients Skype Entreprise, les clients Lync ou les téléphones IP Skype Entreprise en tant qu’agents.

## <a name="call-queue-cmdlets"></a>Cmdlets de file d’attente d’appels

Vous pouvez également utiliser des Windows PowerShell pour créer et configurer des files d’attente d’appels. Voici les cmdlets que vous utilisez pour gérer une file d’attente d’appels.

- [New-CsCallQueue](/powershell/module/skype/new-CsCallQueue)

- [Set-CsCallQueue](/powershell/module/skype/set-CsCallQueue)

- [Get-CsCallQueue](/powershell/module/skype/get-CsCallQueue)

- [Remove-CsCallQueue](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a>Voir aussi

[Voici les avantages du système téléphonique](here-s-what-you-get-with-phone-system.md)

[Obtention de numéros de téléphone de service](getting-service-phone-numbers.md)

[Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[New-CsOnlineApplicationInstance](/powershell/module/skype/new-csonlineapplicationinstance)

[Présentation de Windows PowerShell et Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
