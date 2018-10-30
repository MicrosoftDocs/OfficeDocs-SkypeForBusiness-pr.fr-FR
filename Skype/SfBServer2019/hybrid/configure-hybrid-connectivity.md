---
title: Configurer la connectivité hybride
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instructions pour l’implémentation de connectivité hybride entre Skype pour Business Server et Skype pour Business Online.
ms.openlocfilehash: a85b899407971ebdad0ac4c46096a6feade3fbcd
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839558"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Configurer la connectivité hybride entre Skype pour Business Server et Office 365
 
**Résumé :** Lisez cette rubrique pour savoir comment configurer la connectivité hybride entre Skype pour Business Server et Skype pour Business Online ou équipes.  Connectivité hybride permet de déplacer vos utilisateurs locaux vers Skype pour Business en ligne ou les équipes et permet aux utilisateurs de tirer parti des services en nuage.
  
Avant d’effectuer les étapes décrites dans cette rubrique, vous devez avoir lu [planifier la connectivité hybride entre Skype pour Business Server et Office 365](plan-hybrid-connectivity.md).
  
Le tableau suivant répertorie les tâches requises pour configurer Skype pour BDC hybride et fournit des liens vers les articles associés pour plus d’informations.
  
|**Étape**|**Description**|
|:-----|:-----|
|Créer un compte client pour Office 365 et activer des Skype pour Business en ligne  <br/> |Découvrez Office 365 et Skype pour les entreprises en ligne sur [Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Pour vérifier que votre environnement est prêt pour Office 365, reportez-vous à l’article [Configuration système requise](https://products.office.com/en-US/office-system-requirements).  <br/> Pour plus d’informations sur la configuration d’Office 365, reportez-vous à l’article [Prise en main d’Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Ajouter votre domaine à votre client Office 365 et vérifier la propriété  <br/> | Vous devez l’ajouter à votre client Office 365, puis suivre la procédure de validation avec Office 365. Cela permet de confirmer que vous êtes bien le propriétaire du domaine. <br/> Pour ajouter votre domaine à votre client Office 365, suivez les étapes décrites dans [Ajouter un domaine à Office 365](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).  <br/> |
|Préparer la synchronisation Active Directory  <br/> |La synchronisation Active Directory maintient votre Active Directory local en permanence synchronisé avec Office 365. Cela vous permet de créer des versions synchronisées de chaque groupe et compte d’utilisateur et de synchroniser la liste d’adresses globale de votre environnement Microsoft Exchange Server local vers Microsoft Exchange Online. Pour plus d’informations, voir [répertoires intégrer votre locale avec Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).  <br/>  **Important :** Vous devez synchroniser les comptes Active Directory pour tous les Skype pour les utilisateurs professionnels de votre organisation entre votre organisation locale et les déploiements en ligne, même si les utilisateurs ne sont pas déplacés vers Skype pour Business Online. Si vous ne synchronisez pas tous les utilisateurs, la communication entre les utilisateurs locaux et en ligne dans votre organisation risque de ne pas fonctionner comme vous le souhaitez.           |
| Configurer Skype pour un environnement hybride Business | Cette expression se compose de trois étapes :  <br>1. configurer votre service de périphérie sur site pour la fédération avec Skype pour Business Online. <br> 2. configurer votre Skype pour Business Online client pour un espace d’adressage SIP partagé. <br> 3. configurer l’authentification, si nécessaire.    <br> Pour plus d’informations, voir [Configurer les Skype pour un environnement hybride Business](configure-federation-with-skype-for-business-online.md).
|Déplacement des utilisateurs pilotes  <br/> |Après avoir terminé les étapes pour préparer et configurer votre environnement pour Skype pour Business Online, vous pouvez démarrer le déplacement d’utilisateurs pilotes vers votre client Office 365 en ligne. Pour plus d’informations, voir [déplacer des utilisateurs à partir de sur site à Skype pour Business Online](move-users-from-on-premises-to-skype-for-business-online.md) et [déplacer les utilisateurs à partir de sur site aux équipes](move-users-from-on-premises-to-Teams.md).  <br/> | 

  