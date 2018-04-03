---
title: Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/23/2018
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
- LIL_Placement
description: 'See how to  let people who are using Skype for Business contact Skype for Business users from outside your organization and add them to their list of contacts. '
ms.openlocfilehash: c9867478474bd344674b1392af4d909931760b8c
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2018
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a>Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype

Avec Skype Entreprise, vos utilisateurs peuvent rechercher et contacter par messagerie instantanéet toute personne utilisant Skype, l'application gratuite ! Cet article vous indique comment procéder pour leur permettre d'ajouter des contacts Skype. 
  
Pour cela, vous devez disposer [d’autorisations d’administrateur](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) dans Office 365.
  
1. Connectez-vous à l'aide de votre Office 365 compte d'administrateur sur [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).
    
2. Dans le Centre d'administration Office 365, allez dans **Centres d'administration** > **Skype Entreprise**. 
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. Dans le **centre d'administration de Skype Entreprise**, sélectionnez **Organisation** > **Communications externes**. 
    
4. Par défaut, vos utilisateurs peuvent communiquer avec quiconque utilisant Skype Entreprise (si la configuration de votre pare-feu le permet). 
    
    ![Choose Let people use Skype for Business to communicate with Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    Si vous souhaitez autoriser vos utilisateurs à communiquer avec des contacts Skype, mais pas ceux utilisant Skype Entreprise, sélectionnez **Activé uniquement pour les domaines autorisés**. Lorsque vous autorisez le contact avec des utilisateurs Skype, skype.com est automatiquement ajouté à la liste des domaine autorisés à l'arrière-plan. 
    
    Pour autoriser la communication avec toutes les organisations à travers le monde utilisant Skype Entreprise, excepté certaines d'entre elles, sélectionnez **Activer sauf pour les domaines bloqués** et sélectionnez **+** pour ajouter ces domaines. Tout le monde pourra vous contacter, sauf les personnes appartenant aux domaines spécifiques. Cette option peut être choisie par certaines entreprises si, par exemple, elles sont en litige et doivent s'assurer qu'aucun contact n'a lieu avec l'autre entreprise.
    
5. Choisissez **Autoriser les utilisateurs à employer Skype Entreprise pour communiquer avec des utilisateurs Skype extérieurs à votre organisation**. 
    
6.  Si vous utilisez le pare-feu Windows, Skype Entreprise ouvre automatiquement les ports nécessaires.
    
    Si votre organisation utilise une autre solution pour empêcher les ordinateurs sur le réseau de se connecter à Internet, assurez-vous que les ordinateurs clients peuvent accéder à toutes les [adresses IP et URL](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) pour la connectivité Skype et la recherche dans l’annuaire Skype. Il vous faudra peut-être les ajouter à la liste autorisée dans votre pare-feu ou la configuration de votre infrastructure proxy.
    
7. **ATTENDEZ JUSQU'À 24 HEURES POUR EFFECTUER UN TEST**. Chaque fois que vous modifiez les paramètres de communications externes, jusqu'à 24 heures peuvent être nécessaires pour que les modifications soient appliquées à tous les centres de données.
    
8. Montrez à vos utilisateurs comment rechercher et ajouter des contacts Skype à leur liste des contacts Skype Entreprise. Dirigez-les vers [Rechercher des personnes dans Skype Entreprise](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).
    
## <a name="test-and-troubleshoot"></a>Test et dépannage

Pour tester votre configuration, vous devez disposer d'un contact qui ne soit pas situé derrière le pare-feu de votre entreprise. Il peut se connecter à Skype à l'aide d'un compte Gmail, Outlook.com, ou de tout autre type de compte de messagerie.
  
1. Une fois vos paramètres de communication externe modifiés, **ATTENDEZ JUSQU'À 24 HEURES POUR EFFECTUER UN TEST**.
    
2. Déconnectez-vous de Skype Entreprise, puis reconnectez-vous pour afficher l'option de recherche dans l'annuaire Skype. 
    
    ![When Skype Directory is highlighted, you can search for people who have Skype accounts.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. Dans Skype Entreprise, recherchez votre contact Skype et envoyer une demande de discussion. 
    
    Si votre message ne peut pas être envoyé en raison d’une stratégie de votre société, vous devez vérifier à nouveau les [paramètres de votre pare-feu](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). 
    
4. Une autre solution permettant de vérifier si le problème se situe au niveau de votre pare-feu consiste à utiliser Skype Entreprise à partir d'un emplacement Wi-Fi non situé derrière votre pare-feu, par exemple un café, pour envoyer une demande de conversation à votre contact Skype. 
    
  - **Si votre contact Skype ne reçoit pas votre demande**, demandez-lui de vous envoyer une demande de conversation. Si le problème était lié à l'établissement de connexion entre Skype et Skype Entreprise, cela permettra de le résoudre.
    
  - Si le message a pu être envoyé depuis le café et non depuis votre bureau, vous savez alors que le problème est lié à votre pare-feu. 
    
## <a name="what-you-can-and-cant-do"></a>Opérations possibles et impossibles

- **Skype EntrepriseSur Mac**, vous ne pouvez pas rechercher et communiquer avec les contacts Skype.
    
- Lorsque la recherche dans l’annuaire est activée, vous pouvez rechercher et trouver des utilisateurs de Skype et de Skype Entreprise. Si, pour une raison quelconque, vous ne les trouvez pas en les recherchant dans l’annuaire, vous pouvez leur envoyer une demande de contact, et leur demander de se connecter à Skype et de l’accepter pour pouvoir échanger des messages instantanés avec eux. 
    
- Il est impossible d'autoriser la connexion par MI avec d'autres fournisseurs de MI, tels que Google ou Facebook. Vous ne pouvez pas utiliser Skype Entreprise pour envoyer des SMS.

- Il n’est pas possible d’enregistrer des appels vidéo ou audio entre un contact Skype et un contact Skype Entreprise.
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a>Quelles sont les fonctionnalités disponibles lors de l’ajout de contacts Skype ?

Les contacts Skype connectés avec leur compte Microsoft (anciennement Windows Live ID) ne disposent pas de l’ensemble des fonctionnalités lorsqu’ils communiquent avec vos utilisateurs de Skype Entreprise.
  
|**Disponible avec des contacts Skype**|**Fonctions non disponibles pour les contacts Skype**|
|:-----|:-----|
| Conversations vidéo <br/>  Messagerie instantanée de personne à personne <br/>  Présence <br/> | Conversations à plusieurs par messagerie instantanée <br/>  Conversions audio et vidéo avec trois personnes au minimum <br/>  Partage du bureau et de programmes <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Rubriques connexes

[Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise](allow-users-to-contact-external-skype-for-business-users.md)
  
[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)

  
 