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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: "Découvrez comment ajouter une adresse d'urgence à votre compte Skype Entreprise. "
ms.openlocfilehash: b3fab8d41c1b6f59961feee09f5eae888d32b362
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32170914"
---
# <a name="add-change-or-remove-an-emergency-address-for-your-organization"></a>Ajouter, modifier ou supprimer une adresse d’urgence pour votre organisation

Une adresse d’urgence doit être associée à un numéro de téléphone, mais lorsque cela se produit peut varier entre les pays/régions. Aux États-Unis par exemple, vous devez associer une adresse d'urgence lorsque vous attribuez le numéro de téléphone à l'utilisateur. Au Royaume-Uni, vous devez associer une adresse d'urgence au numéro de téléphone lorsque vous obtenez les numéros de téléphone à partir d'Office 365 ou que vous les transférez à partir de votre fournisseur de services actuel.
  
No matter which country/region you are in, it's possible to add a location or locations to an emergency address or remove an emergency address. Depending on the number of physical locations in your organization, you can create them for buildings, floors, and offices. See [What are emergency locations, addresses, and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing) for some details.
  
Pour savoir comment obtenir un forfait d’appel et connaître son coût, voir [Licences de modules complémentaires pour Skype Entreprise et Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
## <a name="add-an-emergency-address"></a>Ajouter une adresse d’urgence

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accéder au **Centre d’administration de Microsoft équipes** > **portail hérité**.
    
3. Dans le volet de navigation de gauche, sélectionnez **Voix** > **Localisations d'urgence**, puis cliquez sur le bouton **Ajouter une nouvelle adresse**.
    
    > [!Important]
    > Vous permet de voir l’option de **voix** dans le volet de navigation gauche dans le Skype entreprise centre d’administration, vous devez d’abord acheter une licence de module complémentaire de **Conférence Audio** , une licence de module complémentaire **Système téléphonique** ou au moins une **licence Enterprise E5**.
    
4. Dans le volet Action, sous **Nouvelle adresse**, saisissez les informations requises dans les champs.
    
5. Après avoir entré toutes les informations de l’adresse, cliquez sur **Valider**.
    
    > [!IMPORTANT]
    > Validating a street or civic address involves making sure that it is legitimate and correctly formatted. It is possible that a partially correct emergency address, such as if you mistyped the name of the city, may still pass validation. Even though it's misspelled and passed validation, the combination of the misspelled name of city along with the other correct parts of the address are enough information to route the call to the appropriate emergency dispatch center. 
    
    > Remarque : Belgique, France, Allemagne, Irlande, pays-bas et en Espagne, il est important de comprendre que pour l’activation d’un numéro de téléphone dans Office 365 à l’emplacement d’urgence, qui doit être utilisé pour obtenir le nombre, la configuration de l’adresse doivent correspondre à la indicatif du numéro de téléphone.
  
    Si l’adresse ne peut être validée, vous pouvez envoyer une demande de validation manuelle en cliquant sur **Envoyer une demande de validation** pour une adresse américaine, ou cliquer sur **Ouvrir une requête de service d’aide pour la validation d'adresse** si vous êtes hors des États-Unis.
    
6. Une fois l'adresse validée, cliquez sur **Enregistrer**.
    
## <a name="change-an-emergency-address"></a>Modifier une adresse d’urgence

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accéder au **Centre d’administration de Microsoft équipes** > **portail hérité**.
    
3. Dans la navigation de gauche, accédez à la **voix** > **emplacements d’urgence**, sélectionnez l’adresse que vous souhaitez modifier, dans le volet Actions, cliquez sur **Modifier**.
    
    > [!IMPORTANT]
    > Vous permet de voir l’option de **voix** dans le volet de navigation gauche dans le Skype entreprise centre d’administration, vous devez d’abord acheter une licence de module complémentaire de **Conférence Audio** , une licence de module complémentaire **Système téléphonique** ou au moins une **licence Enterprise E5**.

4. Apportez les modifications souhaitées, puis cliquez sur **Valider**.

5. Cliquez sur **Enregistrer**.

## <a name="remove-an-emergency-address"></a>Supprimer une adresse d’urgence

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accéder au **Centre d’administration de Microsoft équipes** > **portail hérité**.
    
3. Dans la navigation de gauche, accédez à la **voix** > **emplacements d’urgence**, sélectionnez l’adresse que vous souhaitez supprimer et dans le volet Actions, cliquez sur **Supprimer**.
    
    > [!IMPORTANT]
    > Vous permet de voir l’option de **voix** dans le volet de navigation gauche dans le Skype entreprise centre d’administration, vous devez d’abord acheter une licence de module complémentaire de **Conférence Audio** , une licence de module complémentaire **Système téléphonique** ou au moins une **licence Enterprise E5**.

## <a name="troubleshooting"></a>Résolution des problèmes

**Numéro de l’état « Échec ».**

Après avoir acquis un numéro à partir du portail Office 365, le statut de **« Mise en service »** à **« Échec »**.

Ce problème se produit souvent lorsqu’un nombre est ajouté à partir du portail, à l’aide d’une adresse d’urgence pointant vers un emplacement qui ne correspond pas au code de zone du téléphone.

Pour obtenir plus d’informations sur les numéros qui n’a pas été correctement activés, exécutez le Powershell suivant :
 
> [! SYNTAXE] Get-CsOnlineTelephoneNumber | Where-Object {$_. « Activé » ActivationState - cnotcontains} | fl *

Le résultat, côté d’autres informations telles que la région, id et ActivationState, doit également contenir le CityCode.

**Exemple**, pour un nombre Madrid, la CityCode renvoyée sera « EMEA-ES-tous-M_MA ».

Si en effet une adresse d’urgence incorrecte a été utilisée, assurez-vous que vous avez créé une nouvelle adresse d’urgence correspondant à l’indicatif du nombre et l’affectez au nombre.

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accéder au **Centre d’administration de Microsoft équipes** > **portail hérité**.
    
3. Dans la navigation de gauche, accédez à la **voix** > **Numéros de téléphone**, puis double-cliquez sur celui-ci dans l’état **« Échec »** et dans le menu site droite, sélectionnez **Nouvelle adresse d’urgence**.


Notez qu’après modification de l’adresse en cas d’urgence, statut son devient **« affectation en attente »** et elle peut prendre jusqu'à 24 heures pour activer correctement.

## <a name="related-topics"></a>Rubriques connexes
[Que sont les emplacements, les adresses et le routage d'appel d'urgence ?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)

[Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)

[Conditions générales relatives aux appels d'urgence](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
