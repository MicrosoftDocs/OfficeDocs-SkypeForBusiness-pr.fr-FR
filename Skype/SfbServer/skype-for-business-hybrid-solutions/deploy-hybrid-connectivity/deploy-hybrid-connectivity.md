---
title: Déploiement de la connectivité hybride entre Skype Entreprise Server et Skype Entreprise Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
description: 'Résumé : Lisez cette rubrique pour savoir comment déployer la connectivité hybride entre Skype pour Business Server et Skype pour l’activité en ligne.'
ms.openlocfilehash: 6dfe230088a2f3ecf827f3d8da9b6c9230ed4989
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-hybrid-connectivity-between-skype-for-business-server-and-skype-for-business-online"></a>Déploiement de la connectivité hybride entre Skype Entreprise Server et Skype Entreprise Online
 
**Résumé :** consultez cette rubrique pour découvrir comment déployer la connectivité hybride entre Skype Entreprise Server et Skype Entreprise Online.
  
Avant d’effectuer les étapes de cette rubrique, vous devez avoir lu le [Plan de connectivité hybride entre Skype pour Business Server et Skype pour l’activité en ligne](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).
  
Connectivité hybride entre Skype pour Business Server et Skype pour entreprise en ligne signifie que les utilisateurs d’un domaine, par exemple, contoso.com, sont réparties entre l’utilisation de Skype pour Business Server dans les locaux et Skype pour l’activité en ligne. Certains utilisateurs du domaine sont hébergés en local et certains le sont en ligne. 
  
Le tableau suivant répertorie les étapes nécessaires pour préparer votre environnement pour un déploiement hybride avec Skype Business Online et de Microsoft Office 365. 
  
|**Étape**|**Description**|
|:-----|:-----|
|Créer un compte client pour Office 365 et activer Skype pour professionnels en ligne  <br/> |Obtenir des informations sur Office 365 et Skype pour l’activité en ligne à [Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Pour vous assurer que votre environnement est prêt pour Office 365, reportez-vous à [Configuration système requise](https://go.microsoft.com/fwlink/p/?LinkId=401408).  <br/> Pour plus d’informations sur la configuration d’Office 365, reportez-vous à la section [Mise en route avec Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Ajouter votre domaine à vos clients d’Office 365 et vérifier la propriété  <br/> | Vous devez l’ajouter à votre client Office 365, puis suivre la procédure de validation avec Office 365. Cela permet de confirmer que vous êtes bien le propriétaire du domaine. <br/> Pour ajouter votre domaine à vos clients d’Office 365, suivez les étapes décrites à [Ajouter votre domaine à Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254983).  <br/> |
|Préparer pour la synchronisation de Active Directory  <br/> |Synchronisation Active Directory conserve votre Active Directory local synchronisés en continu avec Office 365. Cela vous permet de créer des versions synchronisées de chaque groupe et compte d’utilisateur et de synchroniser la liste d’adresses globale de votre environnement Microsoft Exchange Server local vers Microsoft Exchange Online. Pour plus d’informations, consultez [Outils d’intégration de répertoire](https://go.microsoft.com/fwlink/p/?LinkId=530320).  <br/> > [!IMPORTANT]> Vous devez synchroniser les comptes Active Directory pour tous les Skype pour les utilisateurs professionnels de votre organisation entre vos locaux et les déploiements en ligne, même si les utilisateurs ne sont pas déplacés à Skype pour l’activité en ligne. Si vous ne synchronisez pas tous les utilisateurs, la communication entre les utilisateurs locaux et en ligne dans votre organisation risque de ne pas fonctionner comme vous le souhaitez.           |
|Déplacement des utilisateurs pilotes  <br/> |Après avoir terminé les étapes pour préparer et configurer votre environnement pour Skype pour professionnels en ligne, vous pouvez commencer à déplacer les utilisateurs pilotes pour vos clients en ligne de Office 365. Reportez-vous à [déplacer les utilisateurs à partir de locaux à Skype pour l’activité en ligne](move-users-from-on-premises-to-skype-for-business-online.md).  <br/> |
|Gestion des utilisateurs dans un déploiement hybride  <br/> |Pour plus d’informations sur la façon de gérer les utilisateurs dans un déploiement hybride, voir [administration d’utilisateurs dans un déploiement hybride](http://technet.microsoft.com/library/6924ed7b-30a9-4be7-b952-90655625f2c8.aspx).  <br/> |
   

