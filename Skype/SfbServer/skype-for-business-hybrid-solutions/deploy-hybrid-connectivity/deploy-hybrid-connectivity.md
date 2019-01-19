---
title: Déployer la connectivité hybride | Skype pour Business Server 2015 en ligne
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
description: 'Résumé : consultez cette rubrique pour découvrir comment déployer la connectivité hybride entre Skype Entreprise Server et Skype Entreprise Online.'
ms.openlocfilehash: 5e97517cab50f344c5be4981ff64553366dd7710
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2019
ms.locfileid: "29348890"
---
# <a name="deploy-hybrid-connectivity-between-skype-for-business-server-and-skype-for-business-online"></a>Déploiement de la connectivité hybride entre Skype Entreprise Server et Skype Entreprise Online

**Résumé :** consultez cette rubrique pour découvrir comment déployer la connectivité hybride entre Skype Entreprise Server et Skype Entreprise Online.
  
Avant d’effectuer les étapes décrites dans cette rubrique, vous devez avoir lu [planifier la connectivité hybride entre Skype pour Business Server et Skype pour Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).
  
Connectivité hybride entre Skype pour Business Server et Skype pour Business Online signifie que les utilisateurs d’un domaine, par exemple, contoso.com, sont répartis entre l’utilisation de Skype pour Business Server localement et Skype pour Business Online. Certains utilisateurs du domaine sont hébergés en local et certains le sont en ligne.
  
Le tableau suivant répertorie les étapes requises pour préparer votre environnement pour un déploiement hybride avec Skype Business Online et de Microsoft Office 365.
  
|Étape|Description|
|:-----|:-----|
|Créer un compte client pour Office 365 et activer des Skype pour Business en ligne  <br/> |Découvrez Office 365 et Skype pour les entreprises en ligne sur [Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Pour vérifier que votre environnement est prêt pour Office 365, reportez-vous à l’article [Configuration système requise](https://products.office.com/en-US/office-system-requirements).  <br/> Pour plus d’informations sur la configuration d’Office 365, reportez-vous à l’article [Prise en main d’Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Ajouter votre domaine à votre client Office 365 et vérifier la propriété  <br/> | Vous devez l’ajouter à votre client Office 365, puis suivre la procédure de validation avec Office 365. Cela permet de confirmer que vous êtes bien le propriétaire du domaine. <br/> Pour ajouter votre domaine à votre client Office 365, suivez la procédure décrite dans l’article [Ajout de mon domaine à Office 365](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).  <br/> |
|Préparer la synchronisation Active Directory  <br/> |La synchronisation Active Directory maintient votre Active Directory local en permanence synchronisé avec Office 365. Cela vous permet de créer des versions synchronisées de chaque groupe et compte d’utilisateur et de synchroniser la liste d’adresses globale de votre environnement Microsoft Exchange Server local vers Microsoft Exchange Online. Pour plus d’informations, reportez-vous à l’article [Outils d’intégration d’annuaire](https://go.microsoft.com/fwlink/p/?LinkId=530320).  <br/>  **IMPORTANT** Vous devez synchroniser les comptes Active Directory pour tous les Skype pour les utilisateurs professionnels de votre organisation entre votre organisation locale et les déploiements en ligne, même si les utilisateurs ne sont pas déplacés vers Skype pour Business Online. Si vous ne synchronisez pas tous les utilisateurs, la communication entre les utilisateurs locaux et en ligne dans votre organisation risque de ne pas fonctionner comme vous le souhaitez.           |
|Déplacement des utilisateurs pilotes  <br/> |Après avoir terminé les étapes pour préparer et configurer votre environnement pour Skype pour Business Online, vous pouvez démarrer le déplacement d’utilisateurs pilotes vers votre client Office 365 en ligne. Voir [déplacer des utilisateurs à partir de sur site à Skype pour Business Online](move-users-from-on-premises-to-skype-for-business-online.md).  <br/> |

## <a name="related-content"></a>Contenu connexe

Pour plus d’informations sur la configuration de la connectivité hybride entre Skype pour Business Server et Office 365, voir [configurer la connectivité hybride entre Skype pour Business Server et Office 365](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/configure-hybrid-connectivity).