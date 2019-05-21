---
title: Ajouter, modifier ou supprimer une adresse d’urgence pour votre organisation
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: f954c67c-b73c-4473-b6cd-a0fbcd0fd4c9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: "Découvrez comment ajouter une adresse d'urgence à votre compte Skype Entreprise. "
ms.openlocfilehash: 5c22875873d2164c14d690523404481a514ef388
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293734"
---
# <a name="add-change-or-remove-an-emergency-address-for-your-organization"></a>Ajouter, modifier ou supprimer une adresse d’urgence pour votre organisation

Une adresse de secours doit être associée à un numéro de téléphone, mais lorsque cela se produit peut varier d’un pays à l’autre. Aux États-Unis par exemple, vous devez associer une adresse d'urgence lorsque vous attribuez le numéro de téléphone à l'utilisateur. Au Royaume-Uni, vous devez associer une adresse d'urgence au numéro de téléphone lorsque vous obtenez les numéros de téléphone à partir d'Office 365 ou que vous les transférez à partir de votre fournisseur de services actuel.
  
No matter which country/region you are in, it's possible to add a location or locations to an emergency address or remove an emergency address. Depending on the number of physical locations in your organization, you can create them for buildings, floors, and offices. See [What are emergency locations, addresses, and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing) for some details.
  
Pour savoir comment obtenir un forfait d’appel et connaître son coût, voir [Licences de modules complémentaires pour Skype Entreprise et Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
## <a name="add-an-emergency-address"></a>Ajouter une adresse de secours

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accédez au > **portail hérité**du **Centre d’administration Microsoft teams**.
    
3. Dans le volet de navigation de gauche, sélectionnez **Voix** > **Localisations d'urgence**, puis cliquez sur le bouton **Ajouter une nouvelle adresse**.
    
    > [!Important]
    > Pour que l’option **voix** s’affiche dans le volet de navigation gauche du centre d’administration de Skype entreprise, vous devez d’abord acheter au moins une licence **entreprise E5**, une licence de composant additionnel du **système téléphonique** ou une licence du composant additionnel **audioconférence** .
    
4. Dans le volet Action, sous **Nouvelle adresse**, saisissez les informations requises dans les champs.
    
5. Après avoir entré toutes les informations relatives à l’adresse, cliquez sur **valider**.
    
    > [!IMPORTANT]
    > Validating a street or civic address involves making sure that it is legitimate and correctly formatted. It is possible that a partially correct emergency address, such as if you mistyped the name of the city, may still pass validation. Even though it's misspelled and passed validation, the combination of the misspelled name of city along with the other correct parts of the address are enough information to route the call to the appropriate emergency dispatch center. 
    
    > Remarque: en Belgique, en France, en Allemagne, en Irlande, en Pays-Bas et en Espagne, il est important de comprendre qu’pour activer correctement un numéro de téléphone dans Office 365, le paramétrage d’adresse dans l’emplacement d’urgence, qui est utilisé pour acquérir le numéro, doit correspondre au indicatif du numéro de téléphone.
  
    Si l’adresse ne peut être validée, vous pouvez envoyer une demande de validation manuelle en cliquant sur **Envoyer une demande de validation** pour une adresse américaine, ou cliquer sur **Ouvrir une requête de service d’aide pour la validation d'adresse** si vous êtes hors des États-Unis.
    
6. Une fois l'adresse validée, cliquez sur **Enregistrer**.
    
## <a name="change-an-emergency-address"></a>Modification d’une adresse de secours

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accédez au > **portail hérité**du **Centre d’administration Microsoft teams**.
    
3. Dans le volet de navigation de gauche, accédez à**emplacements d’urgence**de la **voix** > , sélectionnez l’adresse à modifier, puis, dans le volet action, cliquez sur **modifier**.
    
    > [!IMPORTANT]
    > Pour que l’option **voix** s’affiche dans le volet de navigation gauche du centre d’administration de Skype entreprise, vous devez d’abord acheter au moins une licence **entreprise E5**, une licence de composant additionnel du **système téléphonique** ou une licence du composant additionnel **audioconférence** .

4. Apportez les modifications souhaitées, puis cliquez sur **valider**.

5. Cliquez sur **Enregistrer**.

## <a name="remove-an-emergency-address"></a>Supprimer une adresse de secours

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accédez au > **portail hérité**du **Centre d’administration Microsoft teams**.
    
3. Dans le volet de navigation de gauche **** > , sélectionnez**emplacements d’urgence**, sélectionnez l’adresse que vous voulez supprimer, puis dans le volet action, cliquez sur **supprimer**.
    
    > [!IMPORTANT]
    > Pour que l’option **voix** s’affiche dans le volet de navigation gauche du centre d’administration de Skype entreprise, vous devez d’abord acheter au moins une licence **entreprise E5**, une licence de composant additionnel du **système téléphonique** ou une licence du composant additionnel **audioconférence** .

## <a name="troubleshooting"></a>Résolution des problèmes

**Nombre dans l’État «failed».**

Suite à l’acquisition d’un numéro à partir du portail Office 365, l’état passe de «échec de **mise en service»** à **«échec»**.

Ce problème survient souvent lors de l’ajout d’un numéro à partir du portail, à l’aide d’une adresse d’urgence pointant vers un emplacement qui ne correspond pas à l’indicatif du téléphone.

Pour obtenir des informations supplémentaires sur les numéros qui n’ont pas été activés correctement, exécutez la commande PowerShell suivante:
 
> [! SYNTAXE] get-CsOnlineTelephoneNumber | Where-Object {$ _. ActivationState-cnotcontains "Activated"} | TX

Le résultat, à l’instar des autres informations comme Region, ID et ActivationState, doit également contenir CityCode.

Par **exemple**, dans le cas d’un numéro Madrid, le CityCode renvoyé sera «EMEA-es-All-M_MA».

Si une mauvaise adresse de secours a été utilisée, assurez-vous que vous avez créé une nouvelle adresse d’urgence correspondant à l’indicatif du numéro et que vous lui attribuez le numéro.

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accédez au > **portail hérité**du **Centre d’administration Microsoft teams**.
    
3. Dans le volet de navigation de gauche, sélectionnez**numéros de téléphone** **vocaux** > , puis double-cliquez sur le numéro dans état **«échec»** et dans le menu du site de droite, sélectionnez la **nouvelle adresse de secours**.


Veuillez noter qu’après modification de l’adresse d’urgence, le statut du numéro devient **«affectation en attente»** et il peut s’écouler jusqu’à 24 heures pour que l’activation réussisse.

## <a name="related-topics"></a>Rubriques connexes
[Que sont les emplacements, les adresses et le routage d'appel d'urgence ?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)

[Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)

[Conditions générales relatives aux appels d'urgence](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
