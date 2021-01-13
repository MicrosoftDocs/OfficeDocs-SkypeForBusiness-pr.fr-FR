---
title: Licence logicielle Skype Room System Skype Entreprise
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Lisez cette rubrique pour savoir comment vérifier si vous avez une licence en volume de logiciel Skype Entreprise.
ms.openlocfilehash: 20e04f69ba5a931bae6ac8598567165a7a6043a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833924"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype Room System : licence logicielle Skype Entreprise
 
Lisez cette rubrique pour savoir comment vérifier si vous avez une licence en volume de logiciel Skype Entreprise. 
  
Skype Room System utilise un client Skype Entreprise installé, qui nécessite une licence en volume logicielle. Avant de déployer le premier skype room system, découvrez l’état de la licence en volume du déploiement , à l’aide des serveurs de gestion de clés (KMS) ou des clés d’activation multiples (MAK).
  
## <a name="key-management-servers-kms"></a>Serveurs de gestion de clés (KMS)

Si le service KMS est en place et distribue les activations de licence en volume Skype Entreprise, Skype Room System active automatiquement le client Skype Entreprise. Pour savoir si kmS est en place :
  
À partir d’une invite de commandes, exécutez :  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Pour plus d’informations, voir Comment découvrir les hôtes KMS Office et [Windows via DNS et supprimer des instances non autorisées](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx). 
  
Pour configurer un service KMS, consultez [l’activation KMS d’Office 2013](https://technet.microsoft.com/library/ee624357.aspx) et des clés GVK pour l’activation KMS et [Active Directory d’Office 2013](https://technet.microsoft.com/library/dn385360.aspx)
  
Clé de licence en volume générique Office 2013 pour Lync : 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (cette clé entraîne la recherche d’un service KMS sur le réseau par Skype Room System).)
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Clés d’activation multiples (MAK) à partir du Centre de service de licence en volume (VLSC)

Si le client utilise un autre logiciel de licence en volume, le service informatique gère les activations logicielles et le contrat de licence en volume (VLA) à l’aide du VLSC. Cela permettra également à l’entreprise d’acheter des activations VL Skype Entreprise, après quoi elle peut obtenir une clé MAK pour l’entrée dans la console d’administration Skype Room System.
  
Un client avec un VLA doit connaître ses informations d’identification VLSC, qui seront utilisées pour administrer le contrat et obtenir une mak. En cas de doute, le service financier du client doit être en mesure de confirmer si le client a payé un VLA.
  
Pour obtenir une clé MAK, accédez au Centre de gestion des licences en volume pour afficher les contrats et télécharger les clés de produit (MAK). Pour plus d’informations, voir le Centre de gestion des [licences en volume.](https://www.microsoft.com/Licensing/servicecenter/default.aspx) 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>MAK pour Microsoft 365 ou Office 365 sans accès VLSC

Si le client n’a pas de contrat de licence en volume, les activations skype entreprise seront beaucoup plus difficiles à gérer. Toutefois, les clients Microsoft 365 et Office 365 qui n’ont pas accès au VLSC peuvent obtenir une mak promotionnelle en fournissant les informations suivantes au OEM qui vend Skype Room System :
  
- Nom de la société
    
- Nom, adresse e-mail et numéro de téléphone du contact de déploiement
    
- Nombre de systèmes déployés
    
- Date de déploiement
    
- Si le client dispose d’un gestionnaire de compte technique Microsoft, le nom et les informations de contact du responsable technique de l’analyseur technique
    

