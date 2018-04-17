---
title: Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
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
ms.openlocfilehash: b7700eeaf9a2fdd39d9a25fce93cfd17f42d4b8e
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise

> [!NOTE]
> Skype for Business federation isn't available to Office 365 operated by 21Vianet and Office 365 Germany organizations. 
  
Suivez la procédure décrite dans cet article lorsque :
  
- Vous avez des utilisateurs avec des domaines différents dans votre entreprise. Par exemple, Rob@ContosoEast.com et Ann@ContosoWest.com.
    
- Vous souhaitez que les personnes de votre organisation utilisent Skype Entreprise pour contacter des membres d'entreprises spécifiques en dehors de votre organisation.
    
-You want anyone else in the world who uses Skype for Business to be able to find and contact you, using your email address. S'ils utilisent les paramètres Skype Entreprise par défaut et que vous aussi, cela fonctionnera automatiquement. Sinon, ils devront s'assurer que leur configuration ne bloque pas votre domaine.
    
## <a name="enable-business-to-business-communications-for-your-users"></a>Autoriser les communications entre entreprises pour vos utilisateurs
<a name="bk_preview"> </a>

To see how this works, watch this video:
***
> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=492278f0-6912-47ba-a1d1-00040061cf44&AutoPlayVideo=false]
***

You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 in both organizations to do this.
  
1. Sign in with your Office 365 admin account. 
    
2. Dans le Centre d'administration Office 365, allez dans **Centres d'administration** > **Skype Entreprise**.
    
    ![Sélectionnez le centre d'administration de Skype Entreprise.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. Dans le **centre d'administration de Skype Entreprise**, sélectionnez **Organisation** > **Communications externes**.
    
4. To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.
    
    Ou, si vous souhaitez activer les communications avec toute personne disposant de stratégies Skype Entreprise ouvertes, sélectionnez **Activer sauf pour les domaines bloqués**. Il s'agit du paramètre par défaut.
    
5. Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.
    
6. Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**. Par exemple, dans sa liste de **domaines autorisés**, l'administrateur de l'autre organisation doit entrer le domaine de votre entreprise.
    
7. Si vous utilisez le pare-feu Windows, Skype Entreprise ouvre automatiquement les ports nécessaires.
    
    Si votre organisation utilise un pare-feu différent pour restreindre l'accès à Internet des ordinateurs de votre réseau, assurez-vous que vos ordinateurs clients peuvent accéder aux [URL et plages d'adresses IP Office 365](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) suivants. This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**. For instructions on how to open these ports in your firewall, check the documentation that came with it.
    
    For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).

8. Make sure that the administrator in the organization has also followed these steps.
    
9. **ATTENDEZ JUSQU'À 24 HEURES POUR EFFECTUER UN TEST**. Chaque fois que vous modifiez les paramètres de communications externes, jusqu'à 24 heures peuvent être nécessaires pour que les modifications soient appliquées à tous les centres de données.
    
![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Vous pouvez permettre à vos utilisateurs de rechercher et contacter par messagerie instantanée toute personne utilisant l'application gratuite Skype. To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).
  
## <a name="test-and-troubleshoot"></a>Test et dépannage
<a name="bk_preview"> </a>

 **Le problème que les utilisateurs rencontrent le plus souvent lors de la configuration de la communication entre entreprises est lié aux [URL et plages d'adresses IP Office 365](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).**
  
Pour tester votre configuration, vous devez disposer d'un contact Skype Entreprise qui ne soit pas situé derrière le pare-feu de votre entreprise.
  
1. Une fois vos paramètres de communication externe modifiés, **ATTENDEZ JUSQU'À 24 HEURES POUR EFFECTUER UN TEST**.
    
2. Dans Skype Entreprise, recherchez votre contact dans Skype Entreprise et envoyer une demande de discussion.
    
    If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).
    
3. Demandez à votre contact Skype Entreprise de vous envoyer une demande de discussion. Si vous ne la recevez pas, le problème se situe au niveau de vos paramètres de pare-feu (en supposant que votre contact a confirmé que ses paramètres sont corrects).
    
4. Pour vérifier si le problème provient du pare-feu, vous pouvez également vous déplacer à un endroit disposant d'un réseau Wi-Fi qui ne soit pas derrière votre pare-feu (un café par exemple) et utiliser Skype Entreprise pour envoyer une demande de discussion à votre contact Skype. Si le message est correctement envoyé, cela signifie que le problème est lié à votre pare-feu.
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>Comment trouver des personnes et être trouvé lors d'une connexion avec une autre entreprise.
<a name="bk_preview"> </a>

After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in name: for example, Rob@contoso.com. Then they will need to add the person to their list of contacts.
  
![To find a user in a federated business, you must search for their email address (this is usually also their sign in name).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>Conseils de configuration des communications avec des entreprises fédérées
<a name="bk_preview"> </a>

- Pour configurer la fédération entre Skype Entreprise 2015 et Skype Entreprise Online, consultez cet article TechNet : [Configuration de la fédération avec Skype Entreprise Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).
    
- Pour configurer la fédération entre Lync et Skype Entreprise Online, consultez cet article TechNet : [Configuration de la prise en charge de la fédération pour un client Lync Online](https://technet.microsoft.com/en-us/library/hh202193.aspx).
    
- Lorsque deux utilisateurs Skype Entreprise dans Office 365 communiquent entre eux sur des domaines distincts, ils peuvent uniquement utiliser les fonctionnalités Skype Entreprise (par exemple, des conversations vidéo ou un partage de bureau) qui sont activées dans les deux organisations.
    
- If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox. Ces conversations ne sont pas enregistrées dans le dossier **Historique des conversations** de leur boîte aux lettres.
    
## <a name="turn-off-external-communication-for-specific-individuals"></a>Désactiver la communication externe pour des individus spécifiques
<a name="bk_preview"> </a>

Après l'activation de la communication externe pour l'ensemble de votre entreprise, vous pouvez la désactiver pour des individus spécifiques.
  
1. Sign in with your Office 365 admin account.
    
2. In the Office 365 admin center, go to **Users** > **Active users**.
    
3. Dans la liste des utilisateurs, choisissez l'utilisateur, puis sous **Paramètres supplémentaires**, cliquez sur **Modifier les propriétés de Skype Entreprise**.
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. In the **Skype for Business admin center**, choose **External communications**.
    
    On the **Options** page, all of the choices will be selected. Clear the communications you want to disable. L'image suivante indique que Jakob pourra communiquer avec le personnel d'autres entreprises approuvées, mais pas avec d'autres utilisateurs Skype.
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Cliquez sur **Enregistrer**.
    
> [!NOTE]
> Il est possible que les modifications ne prennent effet qu'après 24 heures. 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a>Rubriques connexes
<a name="bk_preview"> </a>

[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)
  
[Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md)
  
  
 
