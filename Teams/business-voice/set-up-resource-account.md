---
title: Configurer un compte Microsoft 365 Business de ressource Voix
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Découvrez comment configurer un compte de Microsoft 365 Business voix pour une utilisation avec les attendants automatiques.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76e91a650e9e72c21a39d292e32fe5ff8ecbf80b
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130374"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a>Étape 4 : configurer un compte de ressource Voix Entreprise

Dans Microsoft Teams, un compte de ressource est requis pour chaque employé de la file d'attente d'appels ou de service automatique. Des numéros de téléphone de service peuvent également être attribués aux comptes de ressources. Il s'agit de la façon dont vous affectez des numéros de téléphone aux serveurs de service automatiques et aux files d'attente d'appels, ce qui permet aux appelants de l'extérieur Teams d'accéder au attendant automatique ou à la file d'attente d'appels.

## <a name="obtain-virtual-user-licenses"></a>Obtenir des licences utilisateur virtuel

Les comptes de ressources nécessitent une licence pour l'utilisation des files d'attente et des files d'attente automatiques. Vous pouvez utiliser une licence *utilisateur Microsoft 365 Système téléphonique virtuel.*

1. Connectez-vous au Centre d’administration Microsoft 365.
2. Consultez **les**  >    >  **modules add-ons** Pour plus d'informations sur les services de facturation,  >  **voir tous les modules**
3. Faites défiler jusqu'à la fin pour trouver **la Microsoft 365 Système téléphonique – Licence utilisateur** virtuel. Sélectionnez **Détails,** puis **Acheter.**
4. Sur la page d'achat de licences, sélectionnez le nombre de licences utilisateur virtuel que vous souhaitez. Vous avez besoin d'une licence virtuelle pour chaque attendant automatique et chaque file d'attente d'appels que vous prévoyez de configurer. Nous vous recommandons de sélectionner au moins cinq licences afin de pouvoir facilement configurer des files d'attente automatiques et des files d'attente d'appels à l'avenir sans avoir à acheter d'autres licences immédiatement.
5. **Décochez l'autorisation Affecter automatiquement à tous vos utilisateurs sans licence.**
6. Sélectionnez **Découvrir maintenant.**
7. Confirmez votre commande, **sélectionnez Suivant,** puis **Commande.**

> [!NOTE]
> N'oubliez pas que vous devez  **toujours acheter** la licence, même si son coût est nul.

## <a name="create-a-resource-account"></a>Créer un compte de ressource

Une fois que vous avez reçu *votre Microsoft 365 Système téléphonique - Licence* Utilisateur virtuel, vous pouvez créer votre compte de ressource.

![Capture d'écran de l'interface utilisateur Ajouter un compte de ressource](../media/resource-account-add.png)

1. Dans le Teams d'administration, développez les **paramètres** à l'échelle de l'organisation, puis cliquez **sur Comptes de ressources.**
2. Sélectionnez **Ajouter**.
3. Dans le **volet Ajouter un compte de** ressource, remplissez Nom **d'affichage,** puis **Nom d'utilisateur.** Choisissez un nom d'affichage descriptif tel que « employé principal de la ligne automatique » pour décrire l'objectif du compte de ressource.
4. Dans **Type de compte ressource,** sélectionnez Le attendant **automatique.**
5. Sélectionnez **Enregistrer**.

![Capture d'écran d'une liste des comptes de ressources](../media/resource-accounts-page.png)

## <a name="assign-a-license"></a>Attribuer une licence

Après avoir créé votre compte de ressource, vous devez affecter une Microsoft 365 Système téléphonique *utilisateur* virtuel ou *une Système téléphonique* virtuel.

![Capture d'écran de l'interface utilisateur d'attribution de licences dans Microsoft 365 centre d'administration](../media/resource-account-assign-virtual-user-license.png)

1. Dans le centre Microsoft 365 d'administration, allez dans **Utilisateurs**  >  **actifs.**
2. Sélectionnez votre compte de ressource.
1. Sous **l'onglet Licences et** applications, sous **Licences,** sélectionnez **Microsoft 365 Système téléphonique - Utilisateur virtuel.**
1. Sélectionnez **Enregistrer les modifications,** puis **Fermer.**

## <a name="assign-a-service-number"></a>Affecter un numéro de service

![Capture d'écran de l'interface utilisateur affecter un numéro de service](../media/resource-account-assign-phone-number.png)

1. Dans le Teams d'administration, allez dans les **paramètres** à l'échelle de l'organisation, puis **comptes de ressources.** 
1. Sélectionnez le compte de ressource que vous viennent de créer, puis cliquez **sur Affecter/Désaffecter.**
1. Dans la **Téléphone du type de nombre,** sélectionnez En **ligne.**
1. Dans la **zone Numéro de téléphone** affecté, recherchez le numéro à utiliser, puis cliquez sur **Ajouter.** N'oubliez pas d'inclure l'code de pays (par exemple, **+1** 250 555 0012)
1. Cliquez sur **Enregistrer**.
    > [!NOTE]
    > Vous n'avez pas besoin de sélectionner un moyen de contrôle automatique sous **Affecter,** car le attendant automatique à qui vous voulez ajouter le numéro est déjà sélectionné.

> [!div class="nextstepaction"]
> [Étape suivante : affecter des numéros de téléphone à vos utilisateurs](set-up-assign-numbers.md)
