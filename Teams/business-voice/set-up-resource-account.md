---
title: Configurer un compte Microsoft Teams Système téléphonique ressource client
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Découvrez comment configurer un compte de ressource Microsoft Teams Système téléphonique à utiliser avec les attendants automatiques.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a0953ef81ef3128da858733931a43238531e83b6
ms.sourcegitcommit: e86e3824c300c24e022d5cb1848338278a5a96a8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/03/2022
ms.locfileid: "63053243"
---
# <a name="step-4-set-up-a-teams-phone-system-resource-account"></a>Étape 4 : configurer un compte de Teams Système téléphonique ressources

Les comptes de ressources ne sont affectés à aucun utilisateur spécifique. En revanche, les comptes de ressources, qui utilisent une licence d’utilisateur virtuel gratuit, sont utilisés par les appareils et services dans Microsoft 365. Dans Microsoft Teams, les comptes de ressources se font attribuer des numéros de téléphone, puis sont associés aux files d’attente et aux files d’attente automatiques.

En associant des comptes de ressources aux postes de service automatiques et aux files d’attente d’appels, vous pouvez leur ajouter un ou plusieurs numéros de téléphone gratuits ou gratuits. Par exemple, vous pouvez associer un compte de ressource à un numéro toll à un service automatique pour les appelants locaux. Pour les appels longue distance, vous pouvez associer un autre compte de ressource à un numéro gratuit au même employé de service automatique.

Les sections de cet article expliquent comment configurer un compte de ressource et lui attribuer un numéro de téléphone. Plus tard, vous associerez le compte de ressource à un employé de service automatique.

## <a name="obtain-virtual-user-licenses"></a>Obtenir des licences utilisateur virtuel

Les comptes de ressources nécessitent une licence pour l’utilisation des files d’attente et des files d’attente automatiques. Vous pouvez utiliser une licence *utilisateur Microsoft Teams Téléphone Standard - Utilisateur* virtuel.

> [!NOTE]
> Vous ne devez effectuer les étapes suivantes que si vous vous êtes inscrit pour une période d’Teams Téléphone d’essai sous licence d’offre groupée de forfait d’appels. Si vous avez acheté Teams Téléphone des licences groupées de plan d’appels, les licences virtuelles doivent déjà être appliquées à votre compte.
>
> Pour voir si vous avez déjà des licences virtuelles, connectez-vous Microsoft 365 à l’aide d’un compte avec des autorisations d’administrateur global. Ensuite, allez sur Facturation > [vos produits](https://admin.microsoft.com/Adminportal/Home#/subscriptions). Si vous avez des licences virtuelles, elles apparaîtront **Microsoft Teams Téléphone standard - Utilisateur virtuel**.

1. Ouvrez le Centre d'administration Microsoft 365 et connectez-vous avec un utilisateur en tant qu’administrateur global. Il s’agit généralement du compte que vous avez utilisé pour vous inscrire à Microsoft 365.
2. Dans le volet de navigation gauche, allez à <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">**BillingPurchase** > </a> **servicesAdd-onsSee** >  >  **all Add-ons products**.
3. Faites défiler jusqu’à la fin pour trouver **la licence Microsoft Teams Téléphone Standard – Utilisateur** virtuel. **Sélectionnez Détails**, puis **Acheter**.
4. Sur la page d’achat de licences, sélectionnez le nombre de licences utilisateur virtuel que vous souhaitez. Vous avez besoin d’une licence virtuelle pour chaque attendant automatique et chaque file d’attente d’appels que vous prévoyez de configurer. Nous vous recommandons de sélectionner au moins cinq licences afin de pouvoir facilement configurer des files d’attente automatiques et des files d’attente d’appels à l’avenir sans devoir acheter d’autres licences immédiatement.
5. **Décochez Automatiquement l’attribution à tous vos utilisateurs sans licence**.
6. **Sélectionnez Découvrir maintenant**.
7. Confirmez votre commande, **sélectionnez Suivant**, puis **Commande.**

> [!NOTE]
> N’oubliez pas que vous devez  **toujours acheter** la licence, même si son coût est nul.

## <a name="create-a-resource-account"></a>Créer un compte de ressource

Une fois que vous avez reçu *Microsoft Teams Téléphone licence Utilisateur virtuel Standard*, vous pouvez créer votre compte de ressource.

1. Ouvrez le Microsoft Teams d’administration et connectez-vous avec un utilisateur en tant qu’administrateur global. Il s’agit généralement du compte que vous avez utilisé pour vous inscrire à Microsoft 365.
2. Dans le volet de navigation gauche, allez à l’échelle de l’organisation <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**paramètresResource** >  **comptes**</a>.
3. Sélectionnez **Ajouter**.
4. Dans le **volet Ajouter un compte de** ressource, remplissez **le nom d’affichage**, puis le nom **d’utilisateur**. Choisissez un nom d’affichage descriptif tel que « employé principal de la ligne automatique » pour décrire l’objectif du compte de ressource.
5. Dans **Type de compte ressource**, sélectionnez **Le attendant automatique**.
6. Sélectionnez **Enregistrer**.

## <a name="assign-a-license"></a>Attribuer une licence

Après avoir créé votre compte de ressource Microsoft Teams Téléphone, vous devez affecter une licence *standard -* Utilisateur virtuel Teams Téléphone *Standard*.

1. Ouvrez le Centre d'administration Microsoft 365 et connectez-vous avec un utilisateur en tant qu’administrateur global. Il s’agit généralement du compte que vous avez utilisé pour vous inscrire à Microsoft 365.
1. Dans le volet de navigation gauche, allez à <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank">**Utilisateurs Utilisateurs** >  **actifs**</a>.
1. Sélectionnez votre compte de ressource.
1. Sous **l’onglet Licences et** applications, sous **Licences**, sélectionnez **Microsoft Teams Téléphone Standard - Utilisateur virtuel**.
1. **Sélectionnez Enregistrer les modifications**, puis **Fermer**.

## <a name="assign-a-service-number"></a>Affecter un numéro de service

1. Ouvrez le Microsoft Teams d’administration et connectez-vous avec un utilisateur en tant qu’administrateur global. Il s’agit généralement du compte que vous avez utilisé pour vous inscrire à Microsoft 365.
1. Dans le volet de navigation gauche, allez à l’échelle de l’organisation <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**paramètresResource** >  **comptes**</a>.
1. Sélectionnez le compte de ressource que vous viennent de créer, puis cliquez **sur Affecter/Désaffecter**.
1. Dans la **Téléphone du type de nombre**, sélectionnez **En ligne**.
1. Dans la **zone Numéro de téléphone** affecté, recherchez le numéro à utiliser, puis cliquez sur **Ajouter**. N’oubliez pas d’inclure l’code de pays (par exemple, **+1** 250 555 0012)
1. Cliquez sur **Enregistrer**.

> [!div class="nextstepaction"]
> [Étape suivante : affecter des numéros de téléphone à vos utilisateurs](set-up-assign-numbers.md)
