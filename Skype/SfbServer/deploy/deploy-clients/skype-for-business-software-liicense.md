---
title: Skype espace système Skype pour la licence de logiciel d’entreprise
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Consultez cette rubrique pour découvrir comment procéder pour vérifier si vous disposez d’une licence en volume de Skype Entreprise.
ms.openlocfilehash: e91a009c29647031d91e791ba5fd41ccc4578d1e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype Room System : licence du logiciel Skype Entreprise
 
Consultez cette rubrique pour découvrir comment procéder pour vérifier si vous disposez d’une licence en volume de Skype Entreprise. 
  
Système de chambre de Skype utilise un installé Skype pour client d’entreprise, qui nécessite une licence logicielle en volume. Avant de déployer le premier système de salle Skype, déterminer l’état de licence de volume du déploiement - à l’aide de serveurs de gestion de clés (KMS) ou clés d’Activation Multiple (MAK).
  
## <a name="key-management-servers-kms"></a>Serveurs de gestion de clés (KMS)

Si KMS sont en place et distribuera Skype pour les activations de licence de Volume d’activité, le système de salle Skype activera automatiquement le Skype pour client d’entreprise. Pour savoir si vous disposez de KMS :
  
À partir d’une invite de commande, exécutez :`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Pour plus d’informations, consultez [comment identifier les hôtes KMS de Windows et de Office via DNS et de supprimer les instances non autorisées](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx). 
  
Pour configurer un serveur gestionnaire de clés, consultez [activation KMS d’Office 2013](https://technet.microsoft.com/en-us/library/ee624357.aspx) et [GVLKs pour l’activation de KMS et Active Directory de Office 2013](https://technet.microsoft.com/en-us/library/dn385360.aspx)
  
Clé de licence en Volume Office 2013 générique pour Lync : 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (cette clé, le système de salle Skype rechercher un service KMS sur le réseau.)
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Clés d’activation multiple (MAK) à partir du Centre de service de licences en volume (VLSC)

Si le client utilise un autre logiciel avec une licence en volume, le service informatique gérera les activations de logiciel et le contrat de licence en volume (VLA) à l’aide du VLSC. Cela permettra également la société d’achat Skype pour les activations de Business VL, après laquelle la société peut obtenir une clé d’activation multiple pour l’entrée dans la Console d’administration système Skype salle.
  
Un client disposant d’un VLA doit connaître ses informations d’identification VLSC, qui seront utilisées pour administrer le contrat et obtenir une MAK. Si elle est incertaine, département des finances du client doit être en mesure de confirmer si le client a payé une VLA.
  
Pour obtenir une MAK, accédez au Centre de service de licences en volume pour afficher les contrats et télécharger des clés de produit (MAK). Pour plus d’informations, accédez au [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx). 
  
## <a name="mak-for-office-365-without-vlsc-access"></a>MAK pour Office 365 sans accès au VLSC

Si le client ne possède pas un contrat de licence de Volume, Skype pour les activations de Business sera beaucoup plus difficile à gérer. Les clients Office 365 sans accès à gestion des peuvent toutefois obtenir une MAK promotionnelle en fournissant les informations suivantes à l’OEM vendre le système de salle de Skype :
  
- Nom de la société
    
- Nom du contact pour le déploiement, e-mail et numéro de téléphone
    
- Nombre de systèmes déployés
    
- Date de déploiement
    
- Si le client possède un gestionnaire de compte technique Microsoft, nom et les coordonnées de la gestion de comptes techniques
    

