---
title: Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
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
description: 'See how to configure Skype for Business to let users talk to users in another organization, or let outside contacts to them. '
ms.openlocfilehash: d8cac3838550530666c2e7550c616a0b77cfd820
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19500682"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise

> [!NOTE]
> Skype pour la fédération entreprise n’est pas disponible pour Office 365 exécuté par 21Vianet et organisations Office 365 Allemagne. 
  
Suivez la procédure décrite dans cet article lorsque :
  
- Vous avez des utilisateurs avec des domaines différents dans votre entreprise. Par exemple, Rob@ContosoEast.com et Ann@ContosoWest.com.
    
- Vous souhaitez que les personnes de votre organisation utilisent Skype Entreprise pour contacter des membres d'entreprises spécifiques en dehors de votre organisation.
    
-Vous souhaitez quiconque dans le monde qui utilise Skype pour les entreprises pour être en mesure de rechercher et contacter à l’aide de votre adresse de messagerie. S'ils utilisent les paramètres Skype Entreprise par défaut et que vous aussi, cela fonctionnera automatiquement. Sinon, ils devront s'assurer que leur configuration ne bloque pas votre domaine.
    
## <a name="enable-business-to-business-communications-for-your-users"></a>Autoriser les communications entre entreprises pour vos utilisateurs
<a name="bk_preview"> </a>

Vous devez disposer des [autorisations d’administrateur](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) dans Office 365 dans les deux organisations pour effectuer cette opération.

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**
  
1. Connectez-vous avec votre compte d’administrateur Office 365. 
    
2. Dans le Centre d'administration Office 365, allez dans **Centres d'administration** > **Skype Entreprise**.
    
    ![Sélectionnez le centre d'administration de Skype Entreprise.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. Dans le **centre d'administration de Skype Entreprise**, sélectionnez **Organisation** > **Communications externes**.
    
4. Pour configurer la communication avec une entreprise spécifique ou des utilisateurs dans un autre domaine, dans la zone de liste déroulante, cliquez **sur uniquement pour les domaines autorisés**.
    
    Ou, si vous souhaitez activer les communications avec toute personne disposant de stratégies Skype Entreprise ouvertes, sélectionnez **Activer sauf pour les domaines bloqués**. Il s'agit du paramètre par défaut.
    
5. Sous **bloqué ou des domaines autorisés**, choisissez **+** et ajoutez le nom du domaine que vous souhaitez autoriser.
    
6. Assurez-vous que l’administrateur de l’autre organisation est ces étapes dans leur **Skype entreprise centre d’administration**. Par exemple, dans sa liste de **domaines autorisés**, l'administrateur de l'autre organisation doit entrer le domaine de votre entreprise.
    
7. Si vous utilisez le pare-feu Windows, Skype Entreprise ouvre automatiquement les ports nécessaires.
    
    Si votre organisation utilise un pare-feu différent pour restreindre l'accès à Internet des ordinateurs de votre réseau, assurez-vous que vos ordinateurs clients peuvent accéder aux [URL et plages d'adresses IP Office 365](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) suivants. Vous devrez peut-être ajouter des noms de domaines complets pour la sortie autorisés dans votre pare-feu ou votre proxy de configuration de l’infrastructure : ** \*. api.skype.com**, \* **. users.storage.live.com**et **graph.skype.com**. Pour obtenir des instructions sur la façon d’ouvrir ces ports sur votre pare-feu, consultez la documentation fournie avec ce dernier.
    
    Pour obtenir la liste de tous les ports à ouvrir, consultez [Office 365 URL et plages d’adresses IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).

8. Assurez-vous que l’administrateur de l’organisation a également suivi ces étapes.
    
9. **ATTENDEZ JUSQU'À 24 HEURES POUR EFFECTUER UN TEST**. Chaque fois que vous modifiez les paramètres de communications externes, jusqu'à 24 heures peuvent être nécessaires pour que les modifications soient appliquées à tous les centres de données.
    
![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Vous pouvez permettre à vos utilisateurs de rechercher et contacter par messagerie instantanée toute personne utilisant l'application gratuite Skype. Pour plus d’informations, voir [permettent de Skype pour les utilisateurs professionnels Ajouter contacts Skype](let-skype-for-business-users-add-skype-contacts.md).
  
## <a name="test-and-troubleshoot"></a>Test et dépannage
<a name="bk_preview"> </a>

 **Le problème que les utilisateurs rencontrent le plus souvent lors de la configuration de la communication entre entreprises est lié aux [URL et plages d'adresses IP Office 365](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).**
  
Pour tester votre configuration, vous devez disposer d'un contact Skype Entreprise qui ne soit pas situé derrière le pare-feu de votre entreprise.
  
1. Une fois vos paramètres de communication externe modifiés, **ATTENDEZ JUSQU'À 24 HEURES POUR EFFECTUER UN TEST**.
    
2. Dans Skype Entreprise, recherchez votre contact dans Skype Entreprise et envoyer une demande de discussion.
    
    Si vous recevez un message qui est n’a pas pu être envoyée en raison de la stratégie d’entreprise, vous devez vérifier votre [Office 365 URL et plages d’adresses IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).
    
3. Demandez à votre contact Skype Entreprise de vous envoyer une demande de discussion. Si vous ne la recevez pas, le problème se situe au niveau de vos paramètres de pare-feu (en supposant que votre contact a confirmé que ses paramètres sont corrects).
    
4. Pour vérifier si le problème provient du pare-feu, vous pouvez également vous déplacer à un endroit disposant d'un réseau Wi-Fi qui ne soit pas derrière votre pare-feu (un café par exemple) et utiliser Skype Entreprise pour envoyer une demande de discussion à votre contact Skype. Si le message est correctement envoyé, cela signifie que le problème est lié à votre pare-feu.
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>Comment trouver des personnes et être trouvé lors d'une connexion avec une autre entreprise.
<a name="bk_preview"> </a>

Après avoir activé la communication externe avec les autres Skype pour les utilisateurs professionnels, vos utilisateurs trouverez Skype fédéré pour les utilisateurs professionnels en recherchant leur nom de connexion : par exemple, Rob@contoso.com. Ils devrez ensuite ajouter cette personne à sa liste des contacts.
  
![Pour rechercher un utilisateur dans une entreprise fédérée, vous devez rechercher leur adresse de messagerie (il s’agit généralement également leur nom de connexion).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>Conseils de configuration des communications avec des entreprises fédérées
<a name="bk_preview"> </a>

- Pour configurer la fédération entre Skype Entreprise 2015 et Skype Entreprise Online, consultez cet article TechNet : [Configuration de la fédération avec Skype Entreprise Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).
    
- Pour configurer la fédération entre Lync et Skype Entreprise Online, consultez cet article TechNet : [Configuration de la prise en charge de la fédération pour un client Lync Online](https://technet.microsoft.com/en-us/library/hh202193.aspx).
    
- Lorsque deux utilisateurs Skype Entreprise dans Office 365 communiquent entre eux sur des domaines distincts, ils peuvent uniquement utiliser les fonctionnalités Skype Entreprise (par exemple, des conversations vidéo ou un partage de bureau) qui sont activées dans les deux organisations.
    
- Si un Skype pour l’utilisateur d’entreprise dans votre organisation est placé sur une archive ou un litige, toutes les conversations par messagerie instantanée entre cet utilisateur et autres Skype pour les utilisateurs d’entreprise ou Skype seront enregistrées dans les **Éléments récupérables** dans leur boîte aux lettres. Ces conversations ne sont pas enregistrées dans le dossier **Historique des conversations** de leur boîte aux lettres.
    
## <a name="turn-off-external-communication-for-specific-individuals"></a>Désactiver la communication externe pour des individus spécifiques
<a name="bk_preview"> </a>

Après l'activation de la communication externe pour l'ensemble de votre entreprise, vous pouvez la désactiver pour des individus spécifiques.
  
1. Connectez-vous avec votre compte d’administrateur Office 365.
    
2. Dans le centre d’administration Office 365, accédez aux **utilisateurs** > **utilisateurs actifs**.
    
3. Dans la liste des utilisateurs, choisissez l'utilisateur, puis sous **Paramètres supplémentaires**, cliquez sur **Modifier les propriétés de Skype Entreprise**.
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. Dans la **Skype entreprise centre d’administration**, choisissez **communications externes**.
    
    Dans la page **Options** , tous les choix seront sélectionnés. Désactivez les communications que vous souhaitez désactiver. L'image suivante indique que Jakob pourra communiquer avec le personnel d'autres entreprises approuvées, mais pas avec d'autres utilisateurs Skype.
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Cliquez sur **Enregistrer**.
    
> [!NOTE]
> Il est possible que les modifications ne prennent effet qu'après 24 heures. 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a>Rubriques connexes
<a name="bk_preview"> </a>

[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)
  
[Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md)
  
  
 
