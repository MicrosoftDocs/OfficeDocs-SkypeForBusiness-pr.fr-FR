---
title: Licence du logiciel Skype Room System Skype entreprise
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Lisez cette rubrique pour savoir comment vérifier si vous disposez d’une licence en volume de Skype entreprise.
ms.openlocfilehash: a44e95d8cd488e2b12e03ee9848ef3d1b254180c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220924"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype Room System : licence du logiciel Skype entreprise
 
Lisez cette rubrique pour savoir comment vérifier si vous disposez d’une licence en volume de Skype entreprise. 
  
Skype Room System utilise un client Skype entreprise installé, qui nécessite une licence en volume logiciel. Avant de déployer le premier système Skype Room, recherchez l’état de la licence en volume du déploiement à l’aide des serveurs de gestion de clés (KMS) ou des clés d’activation multiples (MAK).
  
## <a name="key-management-servers-kms"></a>Serveurs de gestion de clés (KMS)

Si KMS est en place et distribuera les activations de licence en volume Skype entreprise, le système Skype Room activera automatiquement le client Skype entreprise. Pour savoir si KMS est en place :
  
À partir d’une invite de commandes, exécutez :`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Pour plus d’informations, consultez [la rubrique Comment découvrir les hôtes KMS Office et Windows via DNS et supprimer les instances non autorisées](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx). 
  
Pour configurer un KMS, voir [activation kms d’office 2013](https://technet.microsoft.com/library/ee624357.aspx) et [GVLK pour kms et activation Active Directory d’Office 2013](https://technet.microsoft.com/library/dn385360.aspx)
  
La clé de licence en volume générique Office 2013 pour Lync : 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (cette clé force Skype Room System à rechercher un KMS sur le réseau.)
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Clés d’activation multiple (MAK) à partir du centre de service de licences en volume (VLSC)

Si le client utilise un autre logiciel de licence en volume, le service informatique gère les activations logicielles et le contrat de licence en volume (VLA) à l’aide du VLSC. Cela permettra également à l’entreprise d’acheter des activations de licence en volume Skype entreprise, après quoi la société peut obtenir une MAK pour entrée dans la console d’administration de Skype Room System.
  
Un client avec un VLA doit connaître ses informations d’identification VLSC, qui seront utilisées pour administrer le contrat et obtenir une MAK. Si ce n’est pas le cas, le service financier du client doit être en mesure de confirmer si le client a payé un VLA.
  
Pour obtenir une MAK, accédez au centre de gestion des licences en volume pour afficher les accords et télécharger des clés de produit (MAK). Pour plus d’informations, accédez au [Centre](https://www.microsoft.com/Licensing/servicecenter/default.aspx)de gestion des licences en volume. 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>MAK pour Microsoft 365 ou Office 365 sans accès VLSC

Si le client ne dispose pas d’un contrat de licence en volume, les activations de Skype entreprise seront plus difficiles à gérer. Toutefois, les clients Microsoft 365 et Office 365 sans accès VLSC peuvent obtenir une MAK promotionnelle en fournissant les informations suivantes à l’OEM vendant Skype Room System :
  
- Nom de la société
    
- Nom, adresse de messagerie et numéro de téléphone du contact de déploiement
    
- Nombre de systèmes déployés
    
- Date de déploiement
    
- Si le client a un responsable de compte technique Microsoft, le nom et les informations de contact du TAM
    

