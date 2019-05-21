---
title: Licence logiciel Skype entreprise du système de salle Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Consultez cette rubrique pour découvrir comment procéder pour vérifier si vous disposez d’une licence en volume de Skype Entreprise.
ms.openlocfilehash: d1d04dc6c80d4e7e04b6ed7a946dfc393a308933
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287684"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype Room System : licence du logiciel Skype Entreprise
 
Consultez cette rubrique pour découvrir comment procéder pour vérifier si vous disposez d’une licence en volume de Skype Entreprise. 
  
Le système de salle Skype utilise un client Skype entreprise installé, qui nécessite une licence en volume logiciel. Avant de déployer le premier système de salle Skype, recherchez l’état de la licence en volume du déploiement à l’aide d’un serveur de gestion des clés (KMS) ou d’une clé d’activation multiple (MAK).
  
## <a name="key-management-servers-kms"></a>Serveurs de gestion de clés (KMS)

Si KMS est en place et distribue les activations de licence en volume Skype entreprise, le système de salle Skype active automatiquement le client Skype entreprise. Pour savoir si vous disposez de KMS :
  
À partir d’une invite de commandes, exécutez:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Pour plus d’informations, reportez-vous [à la rubrique découvrir comment découvrir les hôtes Office et kms Windows via DNS et supprimer les instances non autorisées](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx). 
  
Pour configurer un KMS, voir [activation kms d’office 2013](https://technet.microsoft.com/library/ee624357.aspx) et [GVLKs pour kms et activation d’Active Directory d’Office 2013](https://technet.microsoft.com/library/dn385360.aspx)
  
Clé de licence en volume générique Office 2013 pour Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (cette clé force le système de salle Skype à chercher un KMS sur le réseau.)
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Clés d’activation multiple (MAK) à partir du Centre de service de licences en volume (VLSC)

Si le client utilise un autre logiciel avec une licence en volume, le service informatique gérera les activations de logiciel et le contrat de licence en volume (VLA) à l’aide du VLSC. Cela permet également à l’entreprise d’acheter des activations de VL Skype entreprise, après lesquelles l’entreprise peut obtenir une clé d’activation multiple pour une entrée dans la console d’administration du système de salle Skype.
  
Un client disposant d’un VLA doit connaître ses informations d’identification VLSC, qui seront utilisées pour administrer le contrat et obtenir une MAK. Si ce n’est pas le cas, le service Finances du client devrait être en mesure de vérifier si le client a réglé une a VLA.
  
Pour obtenir une MAK, accédez au Centre de service de licences en volume pour afficher les contrats et télécharger des clés de produit (MAK). Pour plus d’informations, accédez au [Centre](https://www.microsoft.com/Licensing/servicecenter/default.aspx)de gestion des licences en volume. 
  
## <a name="mak-for-office-365-without-vlsc-access"></a>MAK pour Office 365 sans accès au VLSC

Si le client ne dispose pas d’un contrat de licence en volume, les activations de Skype entreprise seront beaucoup plus difficiles à gérer. En revanche, les clients Office 365 sans gestion VOLUMEHTTPS://go.Microsoft.com/fwlink/P/?LINKID=329762 Access peuvent obtenir une MAK promotionnelle en fournissant les informations suivantes à l’OEM vendant le système de salle Skype:
  
- Nom de la société
    
- Nom du contact pour le déploiement, e-mail et numéro de téléphone
    
- Nombre de systèmes déployés
    
- Date de déploiement
    
- Si le client a un gestionnaire de compte technique Microsoft, le nom et les informations de contact du TAM
    

