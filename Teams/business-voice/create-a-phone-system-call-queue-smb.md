---
title: Créer une file d’attente d’appels dans Microsoft Teams - Didacticiel petite entreprise
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: dobro
ms.topic: article
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
description: Découvrez comment configurer des files d’attente d’appels avec Microsoft 365 Business Voice.
ms.openlocfilehash: 3e75dbb75d9edffedbf25d42f197d8723e3ef9a4
ms.sourcegitcommit: 66e7b28ba1c0433535eb6a3e7d883851c27d9d1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "51478364"
---
# <a name="create-a-call-queue---small-business-tutorial"></a>Créer une file d’attente d’appels - Didacticiel pour les petites entreprises

Les files d’attente permettent de router les appelants vers des personnes de votre organisation qui peuvent vous aider à répondre à un problème ou une question spécifique. Les appels sont distribués un par un aux personnes dans la file d’attente (appelées *agents).* 

Les files d’attente fournissent les services :

- Message de salutation.

- Musique pendant que des personnes patientent dans une file d’attente.

- Routage des appels *(dans l’ordre* Premier dans, Premier sorti (FIFO) - vers des agents.

- Options de gestion pour le dépassement de capacité et le délai d’attente.

#### <a name="before-you-begin"></a>Avant de commencer

Obtenir un [système téléphonique : des licences utilisateur virtuel si](../teams-add-on-licensing/virtual-user.md) vous ne les avez pas encore. Obtenez une file d’attente pour chaque file d’attente d’appels et chaque traitement automatique que vous prévoyez de configurer. Ces licences sont gratuites. Nous vous suggérons donc d’en obtenir quelques supplémentaires si vous décidez de modifier votre installation ultérieurement.

Étant donné que des agents dans une file d’attente d’appels peuvent appeler pour renvoyer un appel client, envisagez de définir l’ID d’appelant de vos agents d’appel sur votre numéro de téléphone principal ou le numéro d’un service automatique approprié. Pour plus d’informations, voir Gérer les [stratégies d’ID](../caller-id-policies.md) d’appelant dans Microsoft Teams.

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a>Pour configurer votre file d’attente d’appels, suivez ces étapes

# <a name="step-1brcreate-a-team"></a>[Étape 1 <br> Créer une équipe](#tab/create-team)

Lorsque vous créez une file d’attente d’appels, vous pouvez ajouter des utilisateurs individuels à la file d’attente ou utiliser un groupe de sécurité existant, un groupe Microsoft 365 ou une équipe Microsoft Teams. Nous vous recommandons [d’utiliser un canal d’équipe.](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e) Cela permet aux membres de la file d’attente de discuter entre eux, de partager des idées et de créer des documents ou d’autres ressources pour aider vos clients. Une équipe fournit également une boîte vocale qui permet aux appelants de laisser un message après les heures d’ouverture ou si la file d’attente atteint sa capacité maximale.

Pour créer une équipe

1. Tout d’abord, cliquez sur **Teams** dans  la partie gauche de l’application, puis cliquez sur Rejoindre ou créer une équipe en bas de votre liste d’équipes.

2. Cliquez ensuite **sur Créer une équipe** (première carte, coin supérieur gauche).

3. Sélectionnez **Créer une équipe à partir de zéro.**

4. Choisissez ensuite si vous souhaitez une équipe publique ou privée. Nous vous recommandons **d’entrer** privé pour votre file d’attente d’appels pour éviter que des personnes ne se retrouvent involontairement dans la file d’attente en rejoignant l’équipe.

5. Nommez votre équipe et ajoutez une description facultative.

6. Lorsque vous avez terminé, cliquez sur **Créer.**

8. Tapez les noms des personnes que vous voulez avoir dans votre file d’attente d’appels, puis cliquez sur **Ajouter.**

9. Cliquez sur **Fermer**. Les personnes que vous ajoutez à une équipe recevront un e-mail leur faisant savoir qu’elles sont désormais membres de votre équipe et que l’équipe s’affichera dans leur liste d’équipes.

Nous allons ensuite ajouter un canal à utiliser avec la file d’attente d’appels.

Pour ajouter un canal

1. Dans Teams, recherchez l’équipe que vous vient de créer, cliquez sur Autres **options** (...), puis sur **Ajouter un canal.**

2. Tapez un nom et une description pour le canal, puis cliquez sur **Ajouter.**

> [!div class="nextstepaction"]
> [Étape 2 : gestion des comptes de ressources >](https://docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[Étape 2 <br> : comptes de ressources](#tab/resource-account)

Chaque file d’attente d’appels que vous créez nécessite un compte de ressource. Ce compte est similaire à un compte d’utilisateur, sauf qu’il est associé à un moyen de service automatique ou à une file d’attente d’appels au lieu d’une personne. Dans cette étape, nous allons créer le compte, lui attribuer une licence *Microsoft 365 Phone System (* licence utilisateur virtuel), puis l’utiliser pour commencer à créer la file d’attente d’appels.

### <a name="create-a-resource-account"></a>Créer un compte de ressource

Vous pouvez créer un compte de ressource dans le Centre d’administration Teams.

1. Dans le Centre d’administration Teams, développez **les paramètres** à l’échelle de l’organisation, puis cliquez **sur Comptes de ressources.**

2. Cliquez sur **Ajouter**.

3. Dans le **volet Ajouter un compte** de ressource, remplissez Nom **d’affichage,** Nom d’utilisateur et sélectionnez **File** d’attente d’appels pour le type de compte **de ressource.** 

    ![Capture d’écran de l’interface utilisateur Ajouter un compte de ressource](../media/resource-account-add-cq.png)

4. Cliquez sur **Enregistrer**.

Le nouveau compte apparaît dans la liste des comptes.

![Capture d’écran d’une liste des comptes de ressources](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a>Attribuer une licence

Vous devez attribuer une *licence Microsoft 365 Phone System - Utilisateur* virtuel au compte de ressource.

1. Dans le Centre d’administration Microsoft 365, cliquez sur le compte de ressource auquel vous voulez attribuer une licence.

2. Sous **l’onglet Licences et** applications, sous **Licences,** sélectionnez **Microsoft 365 Phone System - Utilisateur virtuel.**

3. Cliquez **sur Enregistrer les modifications.**

    ![Capture d’écran de l’interface utilisateur d’attribution de licences dans le Centre d’administration Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a>Créer une file d’attente d’appel

Nous allons ensuite commencer à créer une file d’attente d’appels et affecter le compte de ressource.

1. Dans le Centre d’administration Teams, **développez Voix,** cliquez **sur Files d’attente d’appels,** puis cliquez sur **Ajouter.**

1. Tapez un nom pour la file d’attente d’appels. Les agents voient ce nom lorsqu’ils reçoivent un appel entrant de la file d’attente.

2. Cliquez **sur Ajouter des comptes,** recherchez le compte de ressource à utiliser avec cette file d’attente d’appels, cliquez sur Ajouter, puis sur **Ajouter.** 

3. Choisissez une langue. Cette langue sera utilisée pour les invites vocales générées par le système et la transcription des messages vocaux (si vous les activez).

    ![Capture d’écran des paramètres de langue et de compte de ressource](../media/call-queue-name-language.png)

4. Indiquez si vous souhaitez lire un message d’accueil pour les appelants lorsqu’ils arrivent dans la file d’attente. Vous devez charger un fichier MP3, WAV ou WMA contenant le message d’accueil à lire.

5. Teams fournit de la musique par défaut aux appelants lorsqu’ils sont en attente dans une file d’attente. Si vous souhaitez lire un fichier audio spécifique, sélectionnez Lire un fichier **audio** et téléchargez un fichier MP3, WAV ou WMA.

> [!NOTE]
> L’enregistrement téléchargé ne peut pas avoir une taille supérieure à 5 Mo.
> La musique par défaut fournie dans les files d’attente d’appels de Teams est gratuite pour toutes les redevances payables par votre organisation. 

> [!div class="nextstepaction"]
> [Étape 3 : appeler les agents >](https://docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[Étape 3 : appeler <br> les agents](#tab/call-agents)

Pour ajouter des agents à la file d’attente d’appels, nous les ajouterons à l’équipe et au canal que nous avons créés précédemment.

1. Sélectionnez **l’option Choisir une** équipe, puis cliquez sur Ajouter un **canal.**
2. Tapez le nom de l’équipe que vous avez créée, sélectionnez-la, puis cliquez sur **Ajouter.**
3. Sélectionnez le canal que vous avez créé pour la file d’attente.
3. Cliquez sur **Appliquer**.

    ![Capture d’écran des paramètres d’utilisateurs et de groupes pour les files d’attente d’appels](../media/call-queue-users-groups.png)

> [!NOTE]
> Lorsque de nouveaux utilisateurs sont ajoutés à l’équipe, jusqu’à huit heures peuvent être s’il s’agit de leur premier appel.

> [!div class="nextstepaction"]
> [Étape 4 : gestion des comptes de >](https://docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[Étape 4 <br> Routage des appels](#tab/call-routing)

Choisissez la méthode de routage des appels que vous voulez utiliser.

1. Définir **le mode Conférence** sur **Automatique.**

2. Choisissez la **méthode de routage** que vous voulez utiliser. Cela détermine l’ordre dans lequel les agents reçoivent les appels de la file d’attente. Nous vous recommandons **le routage en série** ou **l’arrondi.** Choisissez l’une des options ci-après :

    - **Le routage d’Attendant** sonne tous les agents dans la file d’attente en même temps. Le premier appelant à prendre l’appel reçoit l’appel.

    - **Le routage en série** a pour but de faire sonner un par un tous les télét calleurs. Si un agent le fait sans appel ou ne décroche pas, l’appel sonnera sur l’agent suivant et essaiera tous les agents jusqu’à ce qu’il soit choisi ou mis hors appel.

    - **L’arrondi balance** le routage des appels entrants de sorte que chaque agent d’appel reçoie le même nombre d’appels depuis la file d’attente. Cela pourrait être souhaitable dans un environnement de vente entrante afin d’assurer la même opportunité entre tous les agents d’appel.

    - **Les itinéraires inactifs** les plus longs à chaque appel à l’agent inactif la plus longue. (Les agents dont l’état de présence est Absent depuis plus de 10 minutes ne sont pas inclus.)

    ![Capture d’écran des paramètres du mode de conférence et de la méthode de routage](../media/call-queue-conference-mode-routing-method.png)

3. Activer **le routage en fonction des** présences Cela a pour but d’appeler des agents dont le statut de présence **est disponible.**

4. Choisissez si vous voulez autoriser les agents à se désaisser des appels.

5. Définissez une **heure d’alerte** de l’agent pour spécifier combien de temps le téléphone d’un agent sonnera avant que la file d’attente redirige l’appel vers le prochain agent.

    ![Capture d’écran des paramètres de routage, de désinspondage et d’heure d’alerte](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [Étape 5 : dépassement de capacité d'>](https://docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[Étape 5 - <br> Dépassement de capacité d’appel](#tab/call-overflow)

Choisissez comment vous voulez gérer les appels dont le nombre d’appels dépasse le nombre maximal dans la file d’attente.

1. Définissez le **nombre d’appels maximal dans la file d’attente.**

2. Choisissez ce que vous voulez faire lorsque le nombre maximal d’appels est atteint. Vous pouvez déconnecter l’appel ou le rediriger. Nous vous recommandons de rediriger l’appel vers l’une des destinations suivantes :
    - **Personne au nom d’une** personne de votre organisation qui peut recevoir des appels vocux
    - **Application vocale :** un attendant automatique ou une autre file d’attente d’appels. (Choisissez le compte de ressource associé au port automatique ou à la file d’attente d’appels lorsque vous choisissez cette destination.)
    - **Numéro de téléphone externe :** n’importe quel numéro de téléphone. Utilisez ce format : +[code pays][code de zone][numéro de téléphone]
    - **Messagerie vocale** : vous pouvez utiliser la boîte aux lettres vocale de l’équipe que vous avez créée.

    ![Capture d’écran des paramètres de dépassement de capacité d’appel](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [Étape 6 : délai d'>](https://docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[Délai d’appel <br> d’étape 6](#tab/call-timeout)

Choisissez ce que vous voulez faire lorsque les appels sont trop longs dans la file d’attente.

1. Définir le **délai d’attente des appels : temps d’attente maximal.**

2. Choisissez ce que vous voulez faire lorsqu’un appel arrive à la fin. Vous pouvez déconnecter l’appel ou le rediriger. Nous vous recommandons de rediriger l’appel vers l’une des destinations suivantes :
    - **Personne au nom d’une** personne de votre organisation qui peut recevoir des appels vocux
    - **Application vocale :** un attendant automatique ou une autre file d’attente d’appels. (Choisissez le compte de ressource associé au port automatique ou à la file d’attente d’appels lorsque vous choisissez cette destination.)
    - **Numéro de téléphone externe :** n’importe quel numéro de téléphone. Utilisez ce format : +[code pays][code de zone][numéro de téléphone]
    - **Messagerie vocale** : vous pouvez utiliser la boîte aux lettres vocale de l’équipe que vous avez créée.

    ![Capture d’écran des paramètres de délai d’appel](../media/call-queue-timeout-handling.png)

3. Cliquez sur **Enregistrer**.

Cela termine la configuration de votre file d’attente d’appels. Vous pouvez ensuite configurer [un attendant automatique.](create-a-phone-system-auto-attendant-smb.md)

---

