---
title: Créer une file d’attente d’appel
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
description: Apprenez à configurer votre système téléphonique pour les files d’attente d’appels à l’aide de Microsoft Teams, qui fournit un message de bienvenue, de la musique, des appels et d’autres fonctionnalités.
ms.openlocfilehash: 8365761f25ff981cd13770f23a27f4ef8a589b25
ms.sourcegitcommit: 22e2f51abf879b34701064839d0e410758b6a3dd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48220172"
---
# <a name="create-a-call-queue"></a>Créer une file d’attente d’appel

Les files d’attente d’appels constituent une méthode de routage des appelants vers des personnes de votre organisation qui peuvent vous aider avec un problème ou une question spécifique. Les appels sont distribués un par un aux personnes de la file d’attente (qui sont appelés *agents*). 

Les files d’attente d’appels fournissent :

- Message d’accueil.

- Musique pendant que les personnes sont en attente.

- Ordre d’acheminement des appels : pour les agents *, première et première sortie* (FIFO).

- Gestion des options de dépassement de capacité et de délai d’attente.

Vérifiez que vous disposez [d’un plan de lecture pour les standards automatiques d’équipe et les files d’attente d’appels](plan-auto-attendant-call-queue.md) , puis suivez les [étapes de mise](plan-auto-attendant-call-queue.md#getting-started) en route avant de suivre les procédures décrites dans cet article.

Pour configurer une file d’attente d’appels, dans le centre d’administration Teams, développez **voix**, cliquez sur **files d’attente d’appels**, puis cliquez sur **Ajouter**.

## <a name="resource-account-and-language"></a>Compte de ressources et langue

![](media/call-queue-name-language.png)

1. Tapez un nom pour la file d’attente d’appels. Les agents verront ce nom lorsqu’ils recevront un appel entrant de la file d’attente.

2. Cliquez sur **Ajouter**un compte, recherchez le compte de ressource que vous voulez utiliser avec cette file d’attente d’appels, cliquez sur **Ajouter**, puis sur **Ajouter**.

3. Choisissez une langue. Ce langage sera utilisé pour les invites vocales générées par le système et la transcription de la boîte vocale (si vous les activez).

## <a name="greetings-and--hold-music"></a>Faire des vœux et garder de la musique

Spécifiez si vous souhaitez lire un message d’accueil pour les appelants lorsqu’ils arrivent dans la file d’attente. Vous devez charger un fichier MP3, WAV ou WMA contenant le message d’accueil que vous voulez lire.

Teams fournit une musique par défaut aux appelants alors qu’ils sont en attente. Si vous voulez lire un fichier audio spécifique, sélectionnez **lire un fichier audio** et télécharger un fichier mp3, WAV ou WMA.

> [!NOTE]
> L’enregistrement téléchargé ne peut pas dépasser 5 Mo.

## <a name="call-agents"></a>Agent d’appel

Les agents d’appel sélectionnés doivent être l’un des éléments suivants : 

- Utilisateurs en ligne avec une licence de système téléphonique et la voix entreprise activée
- Utilisateurs en ligne avec un plan d’appels
- Utilisateurs de Skype entreprise sur site
- Si vos agents utilisent l’application Microsoft teams pour appeler des files d’attente, elles doivent être en mode TeamsOnly.

![](media/call-queue-users-groups.png)

Vous pouvez ajouter jusqu’à 20 agents de manière individuelle et jusqu’à 200 agents via des groupes.

Pour ajouter un utilisateur à la file d’attente, cliquez sur **Ajouter des utilisateurs**, recherchez l’utilisateur, cliquez sur **Ajouter**, puis sur **Ajouter**.

Pour ajouter un groupe à la file d’attente, cliquez sur **Ajouter des groupes**, recherchez le groupe, cliquez sur **Ajouter**, puis cliquez sur **Ajouter**. Vous pouvez utiliser des listes de distribution, des groupes de sécurité et des groupes Microsoft 365 ou des équipes Microsoft Teams.

> [!NOTE]
> Les nouveaux utilisateurs ajoutés à un groupe peuvent parfois prendre jusqu’à huit heures de réception.

## <a name="call-routing"></a>Routage des appels

![](media/call-queue-conference-mode-routing-method.png)

Le **mode conférence** réduit considérablement la durée nécessaire à la connexion d’un appelant à un agent, une fois que l’agent a accepté l’appel. Pour que le mode conférence fonctionne, les agents de la file d’attente d’appels doivent utiliser un des clients suivants :

  - Dernière version du client de bureau Microsoft Teams, de l’application Android ou de l’application iOS
  - Microsoft teams Phone version 1449/1.0.94.2020051601 ou version ultérieure
  
Les comptes d’équipes des agents doivent être définis sur le mode équipes uniquement. Les agents qui ne satisfont pas les exigences requises ne sont pas inclus dans la liste routage des appels. Nous vous recommandons d’activer le mode Conférence pour vos files d’attente si vos agents utilisent tous des clients compatibles.

> [!NOTE]
> Occupé sur occupé n’est pas pris en charge par le mode conférence. Les agents sur les appels hors file d’attente risquent de se présenter avec un appel de file d’attente d’appels si le routage basé sur la présence n’est pas activé.

La **méthode de routage** détermine l’ordre dans lequel les agents reçoivent des appels à partir de la file d’attente. Sélectionnez l’une des options suivantes :

- Le **routage en standard** sonne tous les agents de la file d’attente en même temps. Le premier agent d’appel pour décrocher l’appel obtient l’appel.

- Le **routage série** sonne tous les agents d’appel un par un dans l’ordre indiqué dans la liste des **agents d’appel** . Si un agent est rejeté ou ne décroche aucun appel, l’appel sonnera sur l’agent suivant et tentera d’essayer tous les agents jusqu’à ce qu’il soit décroché.

- La **répétition** alternée équilibre le routage des appels entrants de telle sorte que chaque agent d’appel obtient le même nombre d’appels à partir de la file d’attente. Cela pourrait être souhaitable dans un environnement de ventes entrantes pour garantir l’égalité des chances entre tous les agents d’appel.

- Temps **inactif** le plus long pour chaque appel de l’agent qui est resté inactif le plus longtemps. Un agent est considéré comme inactif si son état de présence est disponible ou s’il est absent depuis moins de 10 minutes. Les agents dont l’état de présence est absent pendant plus de 10 minutes ne sont pas considérés comme inactifs et ne peuvent pas recevoir d’appels tant qu’ils n’ont pas changé leur présence en disponible. 

![](media/call-queue-presence-agents-time.png)


Le **routage basé sur la présence** utilise l’état de disponibilité des agents d’appel pour déterminer si un agent doit être inclus dans la liste de routage des appels pour la méthode de routage sélectionnée. Les téléopérateurs pour lesquels l’état de disponibilité est défini sur **disponible** figurent dans la liste routage des appels et peuvent recevoir des appels. Les agents dont l’état de disponibilité est défini sur tout autre statut sont exclus de la liste routage des appels et ne reçoivent aucun appel tant que leur état de disponibilité n’a pas été modifié en **disponible**. 

Vous pouvez activer le routage des appels en fonction de la présence avec n’importe quelle méthode de routage.

Si un agent ne peut plus passer d’appel, il n’est pas inclus dans la liste routage des appels, quelle que soit la valeur de son statut de disponibilité. 

> [!NOTE]
> Les agents qui utilisent le client Skype entreprise ne sont pas inclus dans la liste des itinéraires d’appel lorsque le routage basé sur la présence est activé. Si vous avez des agents qui utilisent Skype entreprise, n’activez pas le routage des appels basée sur la présence.

**Durée** de l’alerte d’agent spécifie la durée pendant laquelle le téléphone de l’agent sonnera avant que la file d’attente ne redirige l’appel vers l’agent suivant.

Pour les files d’attente de volume élevé, nous vous recommandons d’utiliser les paramètres suivants :

- **Mode** de conférence **automatique**
- **Méthode de routage** pour le **routage en standard**
- **Routage basé** sur la présence sur **activé**
- **Durée de l’alerte agent :** **20 secondes**

## <a name="call-overflow-handling"></a>Gestion du dépassement des appels

![](media/call-queue-overflow-handling.png)

Le nombre **maximal d’appels dans la file d’attente** spécifie le nombre maximal d’appels qui peuvent patienter dans la file d’attente à tout moment. La valeur par défaut est 50, mais elle peut varier entre 0 et 200. Lorsque cette limite est atteinte, l’appel est géré conformément au paramètre **lorsque le nombre maximal d’appels est atteint** .

Vous pouvez choisir de déconnecter l’appel ou de le rediriger vers l’une des destinations de routage des appels. Par exemple, vous pouvez demander à l’appelant de laisser une boîte vocale pour les agents dans la file d’attente.

> [!NOTE]
> Si le nombre maximum d’appels est défini sur 0, le message d’accueil n’est pas lu.

## <a name="call-timeout-handling"></a>Gestion des délais d’appel

![](media/call-queue-timeout-handling.png)

**Délai d’appel : délai d’attente maximum** spécifie la durée maximale pendant laquelle un appel peut être mis en attente dans la file d’attente avant qu’elle ne soit redirigée ou déconnectée. Vous pouvez spécifier une valeur comprise entre 15 secondes et 45 minutes.

Vous pouvez choisir de déconnecter l’appel ou de le rediriger vers l’une des destinations de routage des appels. Par exemple, vous pouvez demander à l’appelant de laisser une boîte vocale pour les agents dans la file d’attente.

Lorsque vous avez sélectionné les options de temporisation de l’appel, cliquez sur **Enregistrer**.

## <a name="caller-id-for-outbound-calls"></a>ID de l’appelant pour les appels sortants

Dans la mesure où les agents d’une file d’attente d’appels risquent de composer un appel client, envisagez de définir l’identification de l’appelant pour les membres d’une file d’attente pour le numéro de service d’un standard automatique approprié. Pour plus d’informations, voir [gérer les stratégies d’identification d’appelant dans Microsoft teams](caller-id-policies.md) .

## <a name="supported-clients"></a>Clients pris en charge

- Les clients suivants sont pris en charge pour les téléopérateurs dans une file d’attente des appels :

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
    > Les files d’attente d’appels disposant d’un numéro de routage direct ne prennent pas en charge les clients Skype entreprise, les clients Lync ou les téléphones IP Skype entreprise en tant qu’agents.

## <a name="call-queue-cmdlets"></a>Cmdlets de files d’attente d’appels

Vous pouvez également utiliser Windows PowerShell pour créer et configurer des files d’attente d’appels. Voici les applets de passe que vous utilisez pour gérer une file d’attente d’appels.

- [Nouveau-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

## <a name="related-topics"></a>Sujets associés

[Voici les avantages du système téléphonique](here-s-what-you-get-with-phone-system.md)

[Obtention de numéros de téléphone de service](getting-service-phone-numbers.md)

[Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Nouveau-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Présentation de Windows PowerShell et Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
