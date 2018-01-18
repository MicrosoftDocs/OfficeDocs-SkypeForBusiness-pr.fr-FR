---
title: "Autoriser les utilisateurs à contacter Skype externe pour les utilisateurs professionnels"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1_keywords:
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
ms.custom:
- Setup
- LIL_Placement
description: "Reportez-vous à la section Comment configurer Skype pour l’entreprise permettre aux utilisateurs de communiquer avec les utilisateurs dans une autre organisation ou de laisser à l’extérieur des contacts pour les. "
ms.openlocfilehash: e21b89c24618d2296dc44766b8d6ddbd3d527ef7
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>Autoriser les utilisateurs à contacter Skype externe pour les utilisateurs professionnels

> [!NOTE]
> Skype pour la fédération d’entreprise n’est pas disponible pour Office 365 exploités par des 21Vianet et des organisations d’Office 365 Allemagne. 
  
Utilisez les étapes décrites dans cet article lorsque :
  
- Vous avez des utilisateurs sur des domaines différents dans votre entreprise. Par exemple, Rob@ContosoEast.com et Ann@ContosoWest.com.
    
- Vous souhaitez que les personnes de votre organisation d’utiliser Skype pour les entreprises à des contacts dans des entreprises hors de votre organisation.
    
-Vous souhaitez quiconque dans le monde qui utilisent Skype pour les entreprises à être en mesure de rechercher et de vous contacter, à l’aide de votre adresse de courriel. Si vous et utilisez Skype par défaut pour les paramètres de l’entreprise, cela fonctionnera automatiquement. Si ce n’est pas le cas, ils doivent s’assurer que leur configuration ne bloque pas votre domaine.
    
## <a name="enable-business-to-business-communications-for-your-users"></a>Activer les communications business-to-business pour vos utilisateurs
<a name="bk_preview"> </a>

Vous devez disposer [des autorisations d’administration](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) dans Office 365 pour cela.
  
1. Connectez-vous avec votre compte d’administrateur Office 365. 
    
2. Dans le centre d’administration Office 365, accédez aux **Centres d’administration** > **Skype pour les entreprises**.
    
    ![Choisissez le Skype pour le centre d’administration commerciale.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. Dans le **Skype pour le centre d’administration Business**, choisissez **organisation** > **les communications externes**.
    
4. Pour établir une communication avec une entreprise spécifique ou des utilisateurs dans un autre domaine, dans la zone de liste déroulante, cliquez **sur uniquement pour les domaines autorisés**.
    
    OU, si vous souhaitez autoriser la communication avec tout le monde dans le monde qui a ouvert Skype pour des stratégies d’entreprise, cliquez sur **de domaines bloqués à l’exception de**. Il s’agit du paramètre par défaut.
    
5. Sous **bloqué ou domaines autorisés**, choisissez **+** et ajoutez le nom du domaine que vous souhaitez autoriser.
    
6. Assurez-vous que l’administrateur de l’autre organisation est ces mêmes étapes dans leur **Skype pour le centre d’administration commerciale**. Par exemple, dans leur liste **autorisée des domaines** , leur administrateur a besoin d’entrer le domaine de votre entreprise.
    
7. Si vous utilisez le pare-feu Windows, Skype pour entreprise ouvre automatiquement les ports requis.
    
    Si votre organisation utilise une solution de pare-feu différents pour restreindre les ordinateurs de votre réseau de se connecter à Internet, assurez-vous que vos ordinateurs clients sont en mesure d’accéder au suivant [Office 365 URL et les plages d’adresses IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges). Vous devrez peut-être ajouter les noms de domaine complets sortante autorisent de votre pare-feu ou votre proxy configuration de l’infrastructure : ** \*. api.skype.com**, \* **. users.storage.live.com**et **graph.skype.com**. Pour obtenir des instructions sur la façon d’ouvrir ces ports sur votre pare-feu, consultez la documentation qui l’accompagne.
    
    Pour une liste de tous les ports que vous devez ouvrir, consultez [Office 365 URL et les plages d’adresses IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).
    
8. **Attendre jusqu'à 24 heures pour tester**. Chaque fois que vous modifiez les paramètres de communication externe, il peut prendre jusqu'à 24 heures pour que les modifications à remplir dans tous les centres de données.
    
![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) vous pouvez permettre à vos utilisateurs de rechercher et de messagerie instantanée avec tous les utilisateurs de Skype, l’application consommateur libre ! Pour plus d’informations, reportez-vous à la section [permettent de Skype pour les utilisateurs professionnels ajouter les contacts Skype](let-skype-for-business-users-add-skype-contacts.md).
  
## <a name="test-and-troubleshoot"></a>Tester et résoudre les problèmes
<a name="bk_preview"> </a>

 **Le problème le plus courant rencontrés lors du paramétrage de business-to-business communication est l’obtention de leur [Office 365 URL et les plages d’adresses IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) droite.**
  
Pour tester votre installation, vous avez besoin d’un contact sur Skype pour les entreprises qui n’est pas derrière un pare-feu de votre entreprise.
  
1. Après que vous modifiez vos paramètres de communication externe, **attendre jusqu'à 24 heures de TEST**.
    
2. Dans Skype pour les entreprises, rechercher vos contacts dans Skype pour les entreprises et envoyer une demande de conversation.
    
    Si vous obtenez un message qu’il n’a pas pu être envoyée en raison de la stratégie de l’entreprise, vous devez vérifier votre [Office 365 URL et les plages d’adresses IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).
    
3. Demandez à votre Skype pour contact professionnel pour vous envoyer une demande de conversation. Si vous ne recevez pas de leur demande, il s’agit de paramètres de votre pare-feu (en supposant qu’ils avez déjà confirmé que les paramètres du pare-feu sont corrects).
    
4. Un autre moyen de tester si le problème est votre pare-feu consiste à atteindre un emplacement wifi pas derrière le pare-feu comme un café et Skype pour entreprise permet d’envoyer une demande à votre contact d’en discuter. Si le message il traverse, mais pas lorsque vous êtes au travail, vous savez que le problème est votre pare-feu.
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>Comment rechercher des utilisateurs et de trouver, lors de la connexion avec une autre entreprise
<a name="bk_preview"> </a>

Après avoir activé la communication externe avec les autre Skype pour les utilisateurs professionnels, les utilisateurs pourront trouver fédéré Skype pour les utilisateurs professionnels en recherchant leur nom : par exemple, Rob@contoso.com. Ils devront ensuite l’ajouter à leur liste de contacts.
  
![Pour rechercher un utilisateur dans une entreprise fédérée, vous devez rechercher leur adresse e-mail (qui est généralement aussi leur nom d’utilisateur).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>Conseils sur la configuration des communications avec les entreprises fédérées
<a name="bk_preview"> </a>

- Pour configurer la fédération entre Skype pour entreprise 2015 et Skype pour professionnels en ligne, consultez cet article TechNet : [Fédération de configurer avec Skype pour l’activité en ligne](https://technet.microsoft.com/en-us/library/jj205126.aspx).
    
- Pour configurer la fédération entre Lync et Skype pour professionnels en ligne, consultez cet article TechNet : [Configuration de la prise en charge de fédération de client Lync Online](https://technet.microsoft.com/en-us/library/hh202193.aspx).
    
- Lorsque deux Skype pour les utilisateurs professionnels dans Office 365 communiquent entre eux à des domaines distincts, ils peuvent uniquement utiliser Skype pour les fonctionnalités métier (par exemple, des conversations vidéo ou partage de bureau) sont activées dans les deux organisations.
    
- Si un Skype pour les utilisateurs professionnels de votre organisation est placé sur un en Place ou le Litigation Hold, les conversations de messagerie instantanée entre cet utilisateur et autre Skype pour les utilisateurs professionnels ou Skype seront enregistrées dans des **Éléments récupérables** dans leur boîte aux lettres. Ces conversations ne sont pas enregistrées dans le dossier **Historique des Conversations** dans leur boîte aux lettres.
    
## <a name="turn-off-external-communication-for-specific-individuals"></a>Désactiver les communications externes pour des utilisateurs spécifiques
<a name="bk_preview"> </a>

Après avoir activé les communications externes pour l’ensemble de votre entreprise, vous pouvez la désactiver pour des personnes spécifiques uniquement.
  
1. Connectez-vous avec votre compte d’administrateur Office 365.
    
2. Dans le centre d’administration Office 365, consultez la rubrique **utilisateurs** > **utilisateurs actifs**.
    
3. Dans la liste des utilisateurs, cliquez sur l’utilisateur et puis, sous **Paramètres supplémentaires**, cliquez sur **Modifier les Skype pour les propriétés de l’entreprise**.
    
    ![Choisissez Skype pour entreprise](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. Dans le **Skype pour le centre d’administration Business**, choisissez **les communications externes**.
    
    Dans la page **Options** , tous les choix seront sélectionnés. Désactivez les communications que vous souhaitez désactiver. L’image suivante montre que Jakob sera en mesure de communiquer avec des personnes dans d’autres entreprises de confiance, mais pas avec d’autres utilisateurs de Skype.
    
    ![Choisissez des contacts externes](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Cliquez sur **Enregistrer**.
    
> [!NOTE]
> Il se peut que vous deviez attendre jusqu'à 24 heures pour que les modifications prennent effet. 
  


[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a>Rubriques connexes
<a name="bk_preview"> </a>

[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)
  
[Permettent d’ajouter des contacts de Skype Skype pour les utilisateurs professionnels](let-skype-for-business-users-add-skype-contacts.md)
  

