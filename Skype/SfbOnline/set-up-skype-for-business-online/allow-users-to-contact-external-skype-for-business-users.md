---
title: Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
- LIL_Placement
description: 'See how to configure Skype for Business to let users talk to users in another organization, or let outside contacts to them. '
ms.openlocfilehash: bc0a59487d3cfd3e5721d60213d367c750349604
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692939"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise

> [!NOTE]
> La Fédération Skype entreprise n’est pas disponible pour les 365 Office gérées par 21Vianet et les organisations d’Allemagne Office 365. 
  
Suivez la procédure décrite dans cet article lorsque :
  
- Vous avez des utilisateurs avec des domaines différents dans votre entreprise. Par exemple, Rob@ContosoEast.com et Ann@ContosoWest.com.
    
- Vous souhaitez que les personnes de votre organisation utilisent Skype Entreprise pour contacter des membres d'entreprises spécifiques en dehors de votre organisation.
    
- Vous voulez que les autres utilisateurs de Skype entreprise puissent vous trouver et vous contacter à l’aide de votre adresse e-mail. S'ils utilisent les paramètres Skype Entreprise par défaut et que vous aussi, cela fonctionnera automatiquement. Sinon, ils devront s'assurer que leur configuration ne bloque pas votre domaine.
    
## <a name="enable-business-to-business-communications-for-your-users"></a>Autoriser les communications entre entreprises pour vos utilisateurs
<a name="bk_preview"> </a>

Pour cela, vous devez disposer des [autorisations d’administrateur](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) dans Office 365 dans les deux organisations.

![Icône affichant le logo](../images/teams-logo-30x30.png) Microsoft teams **avec le centre d’administration teams**
  
1. Connectez-vous à l’aide de votre compte d’administrateur Office 365. 
    
2. Dans le centre d’administration, accédez **à centre d'** > administration**teams**.
    
    ![Cliquez sur l’administrateur Teams.](../images/MS-Teams-Admin.png)
  
3. Dans le **Centre d’équipes**, sélectionnez **portail** 
 ![hérité **Skype** > , puis choisissez le portail hérité marketing.](../images/SFBlegacy-size65.png)
 
4. Dans le **Centre d’administration de Skype entreprise** , choisissez**communications externes**de l' **organisation** > .
5. Pour configurer une communication avec une entreprise particulière ou avec des utilisateurs d’un autre domaine, dans la liste déroulante, choisissez **activé uniquement pour les domaines autorisés**.
    
    Ou, si vous souhaitez activer les communications avec toute personne disposant de stratégies Skype Entreprise ouvertes, sélectionnez **Activer sauf pour les domaines bloqués**. Il s'agit du paramètre par défaut.
    
6. Sous **domaines bloqués ou autorisés**, **+** sélectionnez et ajoutez le nom du domaine que vous voulez autoriser.
    
7. Assurez-vous que l’administrateur de l’autre organisation effectue les mêmes étapes dans le **Centre d’administration Skype entreprise**. Par exemple, dans sa liste de **domaines autorisés**, l'administrateur de l'autre organisation doit entrer le domaine de votre entreprise.
    
8. Si vous utilisez le pare-feu Windows, Skype Entreprise ouvre automatiquement les ports nécessaires.
    
    Si votre organisation utilise un pare-feu différent pour restreindre l'accès à Internet des ordinateurs de votre réseau, assurez-vous que vos ordinateurs clients peuvent accéder aux [URL et plages d'adresses IP Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) suivants. Cela peut impliquer l’ajout des noms de domaine complets dans la liste des éléments autorisés entrants dans la configuration de votre \*pare-feu ou de votre infrastructure de proxy : ** \*. API.Skype.com**, **. Users.Storage.live.com**et **Graph.Skype.com**. Pour obtenir des instructions sur l’ouverture de ces ports sur votre pare-feu, consultez la documentation qui l’accompagne.
    
    Pour obtenir la liste de tous les ports que vous devez ouvrir, voir [URL et plages d’adresses IP Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).

9. Assurez-vous que l’administrateur de l’organisation a également suivi ces étapes.
    
10. **ATTENDEZ JUSQU'À 24 HEURES POUR EFFECTUER UN TEST**. Chaque fois que vous modifiez les paramètres de communications externes, jusqu'à 24 heures peuvent être nécessaires pour que les modifications soient appliquées à tous les centres de données.
    
![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Vous pouvez permettre à vos utilisateurs de rechercher et contacter par messagerie instantanée toute personne utilisant l'application gratuite Skype. Pour en savoir plus, reportez-vous à la rubrique [autoriser les utilisateurs Skype entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md).
  
## <a name="test-and-troubleshoot"></a>Test et dépannage
<a name="bk_preview"> </a>

 **Le problème que les utilisateurs rencontrent le plus souvent lors de la configuration de la communication entre entreprises est lié aux [URL et plages d'adresses IP Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).**
  
Pour tester votre configuration, vous devez disposer d'un contact Skype Entreprise qui ne soit pas situé derrière le pare-feu de votre entreprise.
  
1. Une fois vos paramètres de communication externe modifiés, **ATTENDEZ JUSQU'À 24 HEURES POUR EFFECTUER UN TEST**.
    
2. Dans Skype Entreprise, recherchez votre contact dans Skype Entreprise et envoyer une demande de discussion.
    
    Si vous recevez un message indiquant qu’il n’a pas pu être envoyé en raison d’une stratégie de l’entreprise, vous devez vérifier vos [URL et plages d’adresses IP Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).
    
3. Demandez à votre contact Skype Entreprise de vous envoyer une demande de discussion. Si vous ne la recevez pas, le problème se situe au niveau de vos paramètres de pare-feu (en supposant que votre contact a confirmé que ses paramètres sont corrects).
    
4. Pour vérifier si le problème provient du pare-feu, vous pouvez également vous déplacer à un endroit disposant d'un réseau Wi-Fi qui ne soit pas derrière votre pare-feu (un café par exemple) et utiliser Skype Entreprise pour envoyer une demande de discussion à votre contact Skype. Si le message est correctement envoyé, cela signifie que le problème est lié à votre pare-feu.
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>Comment trouver des personnes et être trouvé lors d'une connexion avec une autre entreprise.
<a name="bk_preview"> </a>

Après avoir activé les communications externes avec d’autres utilisateurs Skype entreprise, vos utilisateurs peuvent trouver des utilisateurs Skype entreprise fédérés en recherchant leur nom de connexion : par exemple, Rob@contoso.com. Ils devront ensuite ajouter la personne à leurs listes de contacts.
  
![Pour retrouver un utilisateur dans une entreprise fédérée, vous devez rechercher son adresse e-mail (il s’agit généralement de son nom de connexion).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>Conseils de configuration des communications avec des entreprises fédérées
<a name="bk_preview"> </a>

- Pour configurer la Fédération entre Skype entreprise 2015 et Skype entreprise Online, consultez cet article : [configuration de la Fédération avec Skype entreprise Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).
    
- Pour configurer la Fédération entre Lync et Skype entreprise Online, consultez cet article : [configuration de la prise en charge de la Fédération pour un client Lync Online](https://technet.microsoft.com/en-us/library/hh202193.aspx).
    
- Lorsque deux utilisateurs Skype Entreprise dans Office 365 communiquent entre eux sur des domaines distincts, ils peuvent uniquement utiliser les fonctionnalités Skype Entreprise (par exemple, des conversations vidéo ou un partage de bureau) qui sont activées dans les deux organisations.
    
- S’il s’agit d’un utilisateur de Skype entreprise de votre organisation qui est placé sur un site ou une mise en attente de litige, les conversations par messagerie instantanée entre cet utilisateur et les autres utilisateurs Skype entreprise ou Skype seront enregistrées dans les **éléments récupérables** de la boîte aux lettres. Ces conversations ne sont pas enregistrées dans le dossier **Historique des conversations** de leur boîte aux lettres.
    
## <a name="turn-off-external-communication-for-specific-individuals"></a>Désactiver la communication externe pour des individus spécifiques
<a name="bk_preview"> </a>

Après l'activation de la communication externe pour l'ensemble de votre entreprise, vous pouvez la désactiver pour des individus spécifiques.
  
1. Connectez-vous à l’aide de votre compte d’administrateur Office 365.
    
2. Dans le **Centre d’administration, accédez à** > utilisateurs**actifs**.
    
3. Dans la liste des utilisateurs, choisissez l'utilisateur, puis sous **Paramètres supplémentaires**, cliquez sur **Modifier les propriétés de Skype Entreprise**.
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. Dans le **Centre d’administration de Skype entreprise**, choisissez **communications externes**.
    
    Dans la page **options** , tous les choix seront sélectionnés. Effacez les communications que vous souhaitez désactiver. L'image suivante indique que Jakob pourra communiquer avec le personnel d'autres entreprises approuvées, mais pas avec d'autres utilisateurs Skype.
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Cliquez sur **Enregistrer**.
    
> [!NOTE]
> Il est possible que les modifications ne prennent effet qu'après 24 heures. 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a>Rubriques connexes
<a name="bk_preview"> </a>

[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)
  
[Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md)
  
  
 
