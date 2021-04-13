---
title: Configurer un attendant automatique pour Microsoft Teams - Didacticiel pour les petites entreprises
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
- Phone System
description: Découvrez comment configurer et tester les attendants automatiques pour Microsoft 365 Business Voice.
ms.openlocfilehash: 7fb9a9509354f5f6e3a17b2323eeaf2b5872e96e
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656740"
---
# <a name="set-up-an-auto-attendant---small-business-tutorial"></a>Configurer un attendant automatique - Didacticiel pour les petites entreprises

Les employés automatiques peuvent appeler votre organisation et parcourir un système de menus pour parler au service, à la file d’attente d’appels, à une personne ou à un opérateur. Vous pouvez créer des attendants automatiques pour votre organisation avec le Centre d’administration Microsoft Teams.

#### <a name="before-you-begin"></a>Avant de commencer

Obtenez les numéros de service dont vous avez besoin pour les travailleurs automatiques que vous souhaitez rendre accessibles en composant un numéro direct depuis l’extérieur de votre organisation. Cela peut inclure [le transfert de numéros d’un autre fournisseur](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) ou la demande de nouveaux numéros de [service.](../getting-service-phone-numbers.md)

Obtenir un [système téléphonique - Licence utilisateur virtuel](../teams-add-on-licensing/virtual-user.md) pour chaque employé automatique que vous prévoyez de créer. Ces licences sont gratuites. Nous vous suggérons donc d’en obtenir quelques supplémentaires si vous décidez de modifier votre installation ultérieurement.

Si vous souhaitez utiliser un itinéraire des appels [](../set-up-holidays-in-teams.md) différent pour les jours fériés, créez les jours fériés que vous voulez utiliser avant de créer le attendant automatique.

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a>Pour configurer votre attendant automatique, suivez les étapes ci-après

# <a name="step-1brphone-number"></a>[Étape 1 <br> Numéro de téléphone](#tab/phone-number)

Chaque employé automatique que vous créez nécessite un compte de ressource. Ce compte est similaire à un compte d’utilisateur, sauf qu’il est associé à un service de attendant automatique ou à une file d’attente d’appels au lieu d’une personne. Dans cette étape, nous allons créer le compte, lui attribuer une licence *Microsoft 365 Phone System - Utilisateur* virtuel, puis attribuer un numéro de service.

### <a name="create-a-resource-account"></a>Créer un compte de ressource

Vous pouvez créer un compte de ressource dans le Centre d’administration Teams.

1. Dans le Centre d’administration Teams, développez **les paramètres** à l’échelle de l’organisation, puis cliquez sur **Comptes de ressources.**

2. Cliquez sur **Ajouter**.

3. Dans le **volet Ajouter un compte** de ressource, tapez Nom **d’affichage,** Nom d’utilisateur et sélectionnez Le attendant **automatique** pour le type de **compte ressource** 

    ![Capture d’écran de l’interface utilisateur Ajouter un compte de ressource](../media/resource-account-add.png)

4. Cliquez sur **Enregistrer**.

    Le nouveau compte apparaît dans la liste des comptes.

    ![Capture d’écran d’une liste des comptes de ressources](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a>Attribuer une licence

Vous devez attribuer une *licence Microsoft 365 Phone System - Utilisateur* virtuel au compte de ressource.

1. Dans le Centre d’administration Microsoft 365, cliquez sur le compte de ressource auquel vous voulez attribuer une licence.

2. Sous **l’onglet Licences et** applications, sous **Licences,** sélectionnez **Microsoft 365 Phone System - Utilisateur virtuel.**

3. Cliquez **sur Enregistrer les modifications.**

    ![Capture d’écran de l’interface utilisateur d’attribution de licences dans le Centre d’administration Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a>Affecter un numéro de service

Si vous avez besoin que ce moyen de service automatique soit accessible à l’aide d’un numéro de téléphone, affectez ce numéro au compte de ressource.

1. Dans le Centre d’administration Teams, sur la **page** Comptes de ressources, sélectionnez le compte de ressource auquel vous voulez affecter un numéro de service, puis cliquez sur **Affecter/Désaffecter.**

2. Dans le **type de numéro de** téléphone, sélectionnez le type de numéro que vous voulez utiliser.

3. Dans la **zone Numéro de téléphone** affecté, recherchez le numéro à utiliser, puis cliquez sur **Ajouter.**

    ![Capture d’écran de l’interface utilisateur affecter un numéro de service](../media/resource-account-assign-phone-number.png)

4. Cliquez sur **Enregistrer**.

> [!div class="nextstepaction"]
> [Étape 2 : le attendant automatique - Informations générales sur >](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[Étape 2 : <br> Attendant - Informations générales](#tab/general-info)

Pour configurer un attendant automatique

1. Dans le Centre d’administration Teams, **développez Voix,** cliquez sur **Auto attendants,** puis sur **Ajouter.**

2. Tapez un nom pour le attendant automatique dans la zone en haut.

3. Si vous voulez désigner un opérateur, spécifiez la destination des appels vers cet opérateur. Cette option est facultative (mais recommandée). Vous pouvez définir l’option **Opérateur** pour permettre aux appelants de sortir des menus et de parler à une personne désignée.

4. Spécifiez le fuseau horaire de ce attendant automatique. Le fuseau horaire est utilisé pour calculer les heures d’ouverture si vous créez un flux d’appels distinct pour les heures de travail en de suite.

5. Spécifiez une langue pour ce attendant automatique. Il s’agit de la langue qui sera utilisée pour les invites vocales générées par le système.

6. Choisissez si vous voulez activer les entrées vocales. Lorsqu’elle est activée, le nom de chaque option de menu devient un mot clé de reconnaissance vocale. Par exemple, les appelants peuvent dire « Un » pour sélectionner l’option de menu mappée vers la touche 1, ou dire « Ventes » pour sélectionner l’option de menu appelée « Ventes ».

    ![Capture d’écran des paramètres de attendant automatique pour les entrées de nom, d’opérateur, de fuseau horaire, de langue et de voix](../media/auto-attendant-general-info-page-new.png)

7. Cliquez sur **Suivant**.

> [!div class="nextstepaction"]
> [Étape 3 : flux d’appels >](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[Flux d’appels <br> d’étape 3](#tab/call-flow)

Choisir vos options de flux d’appels

1. Choisissez si vous voulez lire un message d’accueil lorsque le attendant automatique répond à un appel.

    Si vous **sélectionnez Lire un fichier audio,** vous pouvez utiliser le bouton Télécharger un fichier pour télécharger un message d’accueil enregistré en tant qu’audio dans .  WAV, . MP3 ou . Format WMA. L’enregistrement ne peut pas avoir une taille supérieure à 5 Mo.

    Si vous sélectionnez Taper un **message** de salutation, le système lit le texte que vous tapez (jusqu’à 1 000 caractères) lorsque le attendant automatique répond à un appel.

    ![Capture d’écran des paramètres de message d’accueil](../media/auto-attendant-call-flow-greeting-message.png)

2. Choisissez la façon dont vous voulez router l’appel.

    Si vous sélectionnez **Déconnecter,** le attendant automatique raccrochera.

    Si vous sélectionnez **Rediriger l’appel,** vous pouvez choisir l’une des destinations de routage des appels.

    Si vous sélectionnez **les options du menu** Lecture, vous pouvez choisir de lire un fichier **audio** ou de taper un **message** d’accueil, puis de choisir entre les options de menu et la recherche dans l’annuaire.

    ![Capture d’écran des paramètres de routage des appels](../media/auto-attendant-call-flow-route-call-message.png)

3. Si vous souhaitez que les appelants utilisent les touches de numérotation pour naviguer, sous Définir les options du **menu,** choisissez ce que vous voulez faire lorsque les appelants appuient sur une touche de numérotation. (Si vous créez ce attendant automatique en tant qu’annuaire de l’entreprise, laissez les options de touche de numérotation vides.)

    Vous pouvez définir n’importe quelle touche de numérotation sur les destinations suivantes :

    - **Une personne de l’organisation,** une personne de votre organisation qui peut recevoir des appels vocux.
    - **Application vocale :** un autre service de messagerie automatique ou une file d’attente d’appels.
    - **Numéro de téléphone externe -** n’importe quel numéro de téléphone. Utilisez ce format : +[code pays][code de zone][numéro de téléphone]
    - **Messagerie vocale** : boîte vocale associée à un groupe Microsoft 365 que vous spécifiez.
    - **Opérateur** (opérateur défini pour le transport automatique). La définition d’un opérateur est facultative. L’opérateur peut être défini comme n’importe quelle autre destination dans cette liste.

    Nous vous recommandons de définir 0 touche sur l’opérateur.

    Pour chaque option de menu, spécifiez les éléments suivants :

    - **Touche de numérotation** (clé du clavier téléphonique pour accéder à cette option).

    - **Commande vocale** : définit la commande vocale qu’un appelant peut lui donner pour accéder à cette option, si les entrées vocales sont activées. Il peut contenir plusieurs mots tels que « Service clientèle » ou « Activités et activités ». 

    - **Redirigez** vers l’endroit où vous souhaitez que l’appel soit reçu lorsque les appelants choisissent cette option. Si vous redirigez vers un service de service automatique ou une file d’attente d’appels, sélectionnez le compte de ressource qui lui est associé.

    ![Capture d’écran des options de touches de numérotation](../media/auto-attendant-call-flow-menu-options-complete.png)

4. Si vous souhaitez utiliser ce attendant automatique comme annuaire de l’entreprise, sous Recherche dans l’annuaire, **sélectionnez Composer par nom.** Lorsque vous activez cette option, les appelants peuvent dire le nom de l’utilisateur ou le taper sur le clavier du téléphone. Tout utilisateur en ligne titulaire d’une licence Phone System est un utilisateur éligible et peut être trouvé avec la numérotation par nom. 

    (Vous pouvez choisir **Numérotation par extension,** toutefois l’extension doit être configurée dans Azure Active Directory.)

5. Une fois que vous avez sélectionné une option **de recherche dans l’annuaire,** cliquez sur **Suivant.**

> [!div class="nextstepaction"]
> [Étape 4 : flux d’appels en de suite après >](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[Étape 4 Après <br> les heures de travail](#tab/after-hours)

Les heures d’ouverture peuvent être définies pour chaque employé de service automatique. Si ce n'est pas le cas, tous les jours et toutes les heures de la semaine seront considérés comme heures d'ouverture, car une planification 24/24 est définie par défaut. Les heures d’ouverture peuvent être définies avec des pauses au cours de la journée et toutes les heures non définies comme heures d’ouverture sont considérées comme des heures d’ouverture en de suite. Vous pouvez définir différentes options de traitement des appels entrants et des messages d’accueil pour les heures de travail en de suite.

Selon la configuration de vos files d’attente et de vos files d’attente automatiques, il se peut que vous devrez uniquement spécifier le routage des appels en de après-heures pour les travailleurs automatiques avec des numéros de téléphone directs.

Si vous souhaitez un routage d’appel distinct pour les appelants en de suite, spécifiez vos heures d’ouverture pour chaque jour. Cliquez **sur Ajouter un nouvel horaire** pour spécifier plusieurs ensembles d’heures pour un jour donné, par exemple, pour spécifier une pause déjeuner.

![Capture d’écran des paramètres de jour et d’heure de fin](../media/auto-attendant-business-hours.png)

Une fois que vous avez spécifié vos heures d’ouverture, choisissez vos options de routage des appels pour les heures de fermeture. Les mêmes options sont disponibles que pour le routage des appels pendant les heures d’ouverture que vous avez spécifié à l’étape **3 (Flux d’appels).**

Cliquez **sur Suivant** lorsque vous avez terminé.

> [!div class="nextstepaction"]
> [Étape 5 : flux d’appels pour les >](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=holidays#steps)

# <a name="step-5brholidays"></a>[Étape 5 <br> Jours fériés](#tab/holidays)

Vous pouvez faire router les appels vers votre service de service automatique différemment les jours fériés et les autres jours. (Si vous ne voulez pas utiliser un flux d’appels différent pour les jours fériés, vous pouvez ignorer cette étape.)



Votre employé automatique peut avoir un flux d’appels pour chaque jour férié que vous avez installé. Vous pouvez ajouter jusqu'à 20 congés planifiés pour chaque standard automatique.

1. Dans la page Paramètres d’appel pour les fêtes, cliquez **sur Ajouter.**

2. Tapez un nom pour ce paramètre de congés.

3. Dans la **dropdown** Jours fériés, choisissez les jours fériés que vous voulez utiliser.

4. Choisissez le type de message d’accueil que vous voulez utiliser.

    ![Capture d’écran des paramètres de vœux pour les fêtes de fin d’année](../media/auto-attendant-holiday-greeting.png)

5. Choisissez si vous voulez **déconnecter ou** **rediriger** l’appel.

6. Si vous choisissez de rediriger l’appel, choisissez sa destination de routage.

    ![Capture d’écran des paramètres d’action d’appel pour les fêtes](../media/auto-attendant-holiday-actions.png)

7. Cliquez sur **Enregistrer**.

    Répétez la procédure si nécessaire pour chaque jour férié supplémentaire.
    
    ![Capture d’écran des paramètres de congés avec jours fériés répertoriés](../media/auto-attendant-holiday-call-settings.png)
    
    Une fois que vous avez ajouté tous vos jours fériés, cliquez sur **Suivant.**

> [!div class="nextstepaction"]
> [Étape 6 : choisir qui fait partir du répertoire >](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[Étape 6 <br> Membres du répertoire](#tab/dial-scope)

*L’étendue de* la numérotation définit les utilisateurs disponibles dans l’annuaire lorsqu’un appelant utilise la numérotation par nom ou la numérotation par extension. La valeur par défaut de **Tous les utilisateurs en** ligne inclut tous les utilisateurs de votre organisation qui sont des utilisateurs en ligne titulaires d’une licence De système téléphonique.

Vous pouvez inclure ou exclure  des utilisateurs  spécifiques en sélectionnant Groupe d’utilisateurs personnalisés sous Inclure ou Exclure, puis en choisissant un ou plusieurs groupes, listes de distribution ou groupes de sécurité Microsoft 365.  Par exemple, vous pouvez exclure des cadres de votre organisation de l’annuaire d’appels. (Si un utilisateur se trouve dans les deux listes, il sera exclu de l’annuaire.)

![Capture d’écran de l’étendue de la numérotation : inclure et exclure des options](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> Jusqu’à 36 heures peuvent être nécessaire pour que le nom d’un nouvel utilisateur soit répertorié dans l’annuaire.

Lorsque vous avez terminé de définir la portée de la numérotation, cliquez sur **Suivant.**

> [!div class="nextstepaction"]
> [Étape 7 : affecter un compte de ressource >](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[Étape 7 <br> : comptes de ressources](#tab/resource-accounts)

Tous les attendants automatiques doivent avoir un compte de ressource associé.  Les travailleurs automatiques de premier niveau auront besoin d’au moins un compte de ressource associé à un numéro de service. Si vous le souhaitez, vous pouvez affecter plusieurs comptes de ressources à un service automatique, chacun avec un numéro de service distinct.

Pour ajouter un compte de ressource

1. Cliquez **sur** Ajouter et recherchez le compte à ajouter. Cliquez **sur** Ajouter, puis sur **Ajouter.**

    ![Capture d’écran du panneau Ajouter des comptes du compte de ressources](../media/auto-attendant-add-resource-account.png)

2. Lorsque vous avez terminé d’ajouter des comptes de service, cliquez sur **Envoyer.**

    ![Capture d’écran d’une liste de comptes de ressources affichant le compte de ressource avec le numéro de service affecté](../media/auto-attendant-resource-account-assigned.png)

    La configuration du attendant automatique est terminée.

---


