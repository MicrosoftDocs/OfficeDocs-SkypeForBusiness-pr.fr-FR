---
title: Autoriser les utilisateurs de Skype Entreprise à ajouter des contacts Skype
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
- LIL_Placement
description: 'Découvrez comment permettre à des personnes qui utilisent Skype Entreprise de contacter des utilisateurs Skype Entreprise externes à votre organisation et à les ajouter à leur liste de contacts. '
ms.openlocfilehash: 77fb8098e7adeebd4267aed7f21153b20abd661b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594838"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a>Autoriser les utilisateurs de Skype Entreprise à ajouter des contacts Skype

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Avec Skype Entreprise, vos utilisateurs peuvent rechercher et contacter par messagerie instantanéet toute personne utilisant Skype, l'application gratuite ! Cet article vous indique comment procéder pour leur permettre d'ajouter des contacts Skype. 
  
Pour ce [faire,](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) vous Microsoft 365 ou vous Office 365 d’autorisations d’administrateur.

![Icône affichant le logo Skype Entreprise](../images/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**
  
1. Connectez-vous à l’Microsoft 365 votre Office 365 administrateur sur [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage) .
    
2. Dans le Centre d’administration, allez dans Centres **d’administration**  >  **Skype Entreprise.** 
    
    ![Sélectionnez le centre d'administration de Skype Entreprise.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. Dans le **centre d'administration de Skype Entreprise**, sélectionnez **Organisation** > **Communications externes**. 
    
4. Par défaut, vos utilisateurs peuvent communiquer avec quiconque utilisant Skype Entreprise (si la configuration de votre pare-feu le permet). 
    
    ![Sélectionnez Autoriser les utilisateurs à employer Skype Entreprise pour communiquer avec Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    Si vous souhaitez autoriser vos utilisateurs à communiquer avec des contacts Skype, mais pas ceux utilisant Skype Entreprise, sélectionnez **Activé uniquement pour les domaines autorisés**. Lorsque vous autorisez le contact avec des utilisateurs Skype, skype.com est automatiquement ajouté à la liste des domaine autorisés à l'arrière-plan. 
    
    Pour autoriser la communication avec toutes les organisations à travers le monde utilisant Skype Entreprise, excepté certaines d'entre elles, sélectionnez **Activer sauf pour les domaines bloqués** et sélectionnez **+** pour ajouter ces domaines. Tout le monde pourra vous contacter, sauf les personnes appartenant aux domaines spécifiques. Cette option peut être choisie par certaines entreprises si, par exemple, elles sont en litige et doivent s'assurer qu'aucun contact n'a lieu avec l'autre entreprise.
    
5. Sélectionnez **Autoriser les utilisateurs à employer Skype Entreprise pour communiquer avec des utilisateurs Skype extérieurs à votre organisation**. 
    
6.  Si vous utilisez le pare-feu Windows, Skype Entreprise ouvre automatiquement les ports nécessaires.
    
    Si votre organisation utilise une autre solution pour empêcher les ordinateurs sur le réseau de se connecter à Internet, assurez-vous que les ordinateurs clients peuvent accéder à toutes les [adresses IP et URL](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) pour la connectivité Skype et la recherche dans l’annuaire Skype. Vous devez peut-être les ajouter à la liste autorisée dans votre pare-feu ou à la configuration de votre infrastructure proxy.
    
7. **ATTENDEZ JUSQU'À 24 HEURES POUR EFFECTUER UN TEST**. Chaque fois que vous modifiez les paramètres de communications externes, jusqu'à 24 heures peuvent être nécessaires pour que les modifications soient appliquées à tous les centres de données.
    
8. Montrez à vos utilisateurs comment rechercher et ajouter des contacts Skype à leur liste des contacts Skype Entreprise. Dirigez-les vers [Rechercher des personnes dans Skype Entreprise](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19).
    
## <a name="test-and-troubleshoot"></a>Test et dépannage

Pour tester votre configuration, vous devez disposer d'un contact qui ne soit pas situé derrière le pare-feu de votre entreprise. Il peut se connecter à Skype à l'aide d'un compte Gmail, Outlook.com, ou de tout autre type de compte de messagerie.
  
1. Après avoir modifié vos paramètres de communication externe, **ATTENDEZ JUSQU’À 24 HEURES POUR EFFECTUER UN TEST**.
    
2. Déconnectez-vous de Skype Entreprise, puis reconnectez-vous pour afficher l’option de recherche dans l’annuaire Skype. 
    
    ![Lorsque l’annuaire Skype est activé, vous pouvez rechercher des personnes qui ont des comptes Skype.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. Dans Skype Entreprise, recherchez votre contact dans Skype et envoyez-lui une demande de conversation. 
    
    Si votre message ne peut pas être envoyé en raison d’une stratégie de votre société, vous devez vérifier à nouveau les [paramètres de votre pare-feu](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). 
    
4. Une autre solution permettant de vérifier si le problème se situe au niveau de votre pare-feu consiste à accéder à un emplacement Wi-Fi non situé derrière votre pare-feu, par exemple un café, et d’utiliser Skype Entreprise pour envoyer une demande de conversation à votre contact Skype. 
    
   - **Si votre contact Skype ne reçoit pas votre demande**, demandez-lui de vous envoyer une demande de conversation. Si le problème était lié à l'établissement de connexion entre Skype et Skype Entreprise, cela permettra de le résoudre.
    
   - Si le message a pu être envoyé depuis le café et non depuis votre bureau, vous savez alors que le problème est lié à votre pare-feu. 
    
## <a name="what-you-can-and-cant-do"></a>Ce que vous pouvez et ne pouvez pas faire

- **Skype Entreprise sur Mac** ne permet de rechercher des contacts Skype et de communiquer avec eux.
    
- Lorsque la recherche dans l’annuaire est activée, vous pouvez rechercher et trouver des utilisateurs de Skype et de Skype Entreprise. Si, pour une raison quelconque, vous ne les trouvez pas en les recherchant dans l’annuaire, vous pouvez leur envoyer une demande de contact, et leur demander de se connecter à Skype et de l’accepter pour pouvoir échanger des messages instantanés avec eux. 
    
- Il est impossible d'autoriser la connexion par MI avec d'autres fournisseurs de MI, tels que Google ou Facebook. Vous ne pouvez pas utiliser Skype Entreprise pour envoyer des SMS.

- Il n’est pas possible d’enregistrer des appels vidéo ou audio entre un contact Skype et un contact Skype Entreprise.
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a>Quelles sont les fonctionnalités disponibles lors de l’ajout de contacts Skype ?

Les contacts Skype connectés avec leur compte Microsoft (anciennement Windows Live ID) ne disposent pas de l’ensemble des fonctionnalités lorsqu’ils communiquent avec vos utilisateurs de Skype Entreprise.
  
|**Disponible avec des contacts Skype**|**Non disponible avec des contacts Skype**|
|:-----|:-----|
| Conversations vidéo <br/>  Messagerie instantanée entre deux personnes <br/>  Présence <br/> | Conversations par messagerie instantanée entre plusieurs parties <br/>  Conversations audio et vidéo avec trois personnes ou plus <br/>  Partage du bureau et de programmes <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Rubriques connexes

[Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise](allow-users-to-contact-external-skype-for-business-users.md)
  
[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)

  
 
