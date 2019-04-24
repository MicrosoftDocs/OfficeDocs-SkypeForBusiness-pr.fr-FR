---
title: Skype salle système Skype pour la licence du logiciel Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Consultez cette rubrique pour découvrir comment procéder pour vérifier si vous disposez d’une licence en volume de Skype Entreprise.
ms.openlocfilehash: e4ba03dacdce0056cb130299f551921042a6790d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207930"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype Room System : licence du logiciel Skype Entreprise
 
Consultez cette rubrique pour découvrir comment procéder pour vérifier si vous disposez d’une licence en volume de Skype Entreprise. 
  
Système de salle Skype utilise un Skype installé client d’entreprise, qui nécessite une licence en volume. Avant de déployer le premier système de salle Skype, déterminer l’état de licence en volume du déploiement - à l’aide des serveurs de gestion de clés (KMS) ou clés d’Activation Multiple (MAK).
  
## <a name="key-management-servers-kms"></a>Serveurs de gestion de clés (KMS)

Si KMS est en place et distribuera Skype des activations de licence en Volume Business, le système de salle Skype activera automatiquement le Skype pour client d’entreprise. Pour savoir si vous disposez de KMS :
  
À partir d’une invite de commandes, exécutez :`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Pour plus d’informations, voir [comment identifier les hôtes Office et Windows KMS via le DNS et supprimer des instances non autorisés](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx). 
  
Pour configurer un KMS, voir [l’activation KMS d’Office 2013](https://technet.microsoft.com/library/ee624357.aspx) et [Gvlk pour l’activation KMS et Active Directory d’Office 2013](https://technet.microsoft.com/library/dn385360.aspx)
  
Clé de licence en Volume Office 2013 générique pour Lync : 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (cette clé, le système de salle Skype rechercher un KMS sur le réseau.)
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Clés d’activation multiple (MAK) à partir du Centre de service de licences en volume (VLSC)

Si le client utilise un autre logiciel avec une licence en volume, le service informatique gérera les activations de logiciel et le contrat de licence en volume (VLA) à l’aide du VLSC. Cela permettra également la société à acheter Skype pour activations Business VL, après laquelle la société peut obtenir une clé MAK d’entrée dans la Console d’administration système Skype salle.
  
Un client disposant d’un VLA doit connaître ses informations d’identification VLSC, qui seront utilisées pour administrer le contrat et obtenir une MAK. Si l’incertitude, finances du client doit être en mesure de confirmer si le client a payé une VLA.
  
Pour obtenir une MAK, accédez au Centre de service de licences en volume pour afficher les contrats et télécharger des clés de produit (MAK). Pour plus d’informations, accédez au [Centre de gestion des licences en Volume](https://www.microsoft.com/Licensing/servicecenter/default.aspx). 
  
## <a name="mak-for-office-365-without-vlsc-access"></a>MAK pour Office 365 sans accès au VLSC

Si le client ne possède pas un contrat de licence en Volume, Skype pour activations Business sera beaucoup plus difficile à gérer. Toutefois, les clients Office 365 sans accès de gestion des peuvent obtenir une clé MAK promotionnelle en fournissant les informations suivantes à l’OEM vente le système de salle de Skype :
  
- Nom de la société
    
- Nom du contact pour le déploiement, e-mail et numéro de téléphone
    
- Nombre de systèmes déployés
    
- Date de déploiement
    
- Si le client dispose d’un gestionnaire de comptes technique Microsoft, nom et les informations de contact de la gestion de comptes techniques
    

