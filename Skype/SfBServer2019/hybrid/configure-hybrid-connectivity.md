---
title: Configurer la connectivité hybride | Déployer Skype pour établir une connexion Business Server 2019
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instructions pour l’implémentation de connectivité hybride entre Skype pour Business Server et Skype pour Business Online.
ms.openlocfilehash: f15744e5cd7608c7cc6b1169844314d0a59c62f0
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2019
ms.locfileid: "29348897"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Configurer la connectivité hybride entre Skype pour Business Server et Office 365

**Résumé :** Lisez cette rubrique pour savoir comment configurer la connectivité hybride entre Skype pour Business Server et les équipes ou Skype pour Business Online.  Connectivité hybride permet de déplacer vos utilisateurs locaux pour les équipes ou Skype pour Business Online et permet aux utilisateurs de tirer parti des services en nuage.
  
Avant d’effectuer les étapes décrites dans cette rubrique, vous devez avoir lu [planifier la connectivité hybride entre Skype pour Business Server et Office 365](plan-hybrid-connectivity.md).
  
Le tableau suivant répertorie les tâches requises pour configurer Skype pour BDC hybride et fournit des liens vers les articles associés pour plus d’informations.
  
|Étape|Description|
|:-----|:-----|
|Créer un compte client pour Office 365   <br/> |Découvrez Office 365 à [Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Pour vérifier que votre environnement est prêt pour Office 365, reportez-vous à l’article [Configuration système requise](https://products.office.com/en-US/office-system-requirements).  <br/> Pour plus d’informations sur la configuration d’Office 365, reportez-vous à l’article [Prise en main d’Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Ajouter votre domaine à votre client Office 365 et vérifier la propriété  <br/> | Vous devez l’ajouter à votre client Office 365, puis suivre la procédure de validation avec Office 365. Cela permet de confirmer que vous êtes bien le propriétaire du domaine. <br/> Pour ajouter votre domaine à votre client Office 365, suivez les étapes décrites dans [Ajouter un domaine à Office 365](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).  <br/> |
|Configurer la synchronisation d’Active Directory  <br/> |La synchronisation Active Directory maintient votre Active Directory local en permanence synchronisé avec Office 365. Cela vous permet de créer des versions synchronisées de chaque compte d’utilisateur et de groupe.  <br/> <br> **Important :** Vous devez synchroniser les comptes Active Directory pour tous les Skype pour les utilisateurs professionnels de votre organisation entre votre organisation locale et les déploiements en ligne, même si les utilisateurs ne sont pas déplacés vers des équipes ou Skype pour Business Online. Si vous ne synchronisez pas tous les utilisateurs, la communication entre les utilisateurs locaux et en ligne dans votre organisation risque de ne pas fonctionner comme vous le souhaitez. Pour plus d’informations, voir [configurer les Azure AD Connect pour les environnements hybrides](configure-azure-ad-connect.md).         |
| Configurer Skype pour un environnement hybride Business | Il existe trois étapes de base : <br><br> 1. configurer votre environnement local à fédérer avec Office 365. <br> 2. configurer votre environnement local pour la gestion de la confidentialité Office 365 et activer l’espace d’adressage SIP partagé avec Office 365.<br> 3. activer l’espace d’adressage SIP partagé dans votre organisation cliente Office 365. <br><br> En outre, si vous avez Exchange locale, vous pouvez choisir de configurer OAuth entre votre Exchange locale et Skype pour les environnements d’entreprise en ligne. <br> <br>Pour plus d’informations, voir [Configurer les Skype pour un environnement hybride Business](configure-federation-with-skype-for-business-online.md).
|Déplacement des utilisateurs pilotes  <br/> |Après avoir terminé les étapes pour préparer et configurer votre environnement pour les équipes ou Skype pour Business Online, vous pouvez démarrer le déplacement d’utilisateurs pilotes vers votre client Office 365 en ligne. Pour plus d’informations, voir [déplacer des utilisateurs à partir de sur site à Skype pour Business Online](move-users-from-on-premises-to-skype-for-business-online.md) et [déplacer les utilisateurs à partir de sur site aux équipes](move-users-from-on-premises-to-Teams.md).  <br/> |