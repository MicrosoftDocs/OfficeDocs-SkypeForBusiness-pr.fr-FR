---
title: Skype Licence logicielle Skype Entreprise système de salle
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Lisez cette rubrique pour savoir comment vérifier si vous avez une licence en volume Skype Entreprise logiciels.
ms.openlocfilehash: 805a9abb6d4d49e653e779edc1d9e1cfb8d2a6ca
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845967"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype Système de salle : Skype Entreprise licence logicielle
 
Lisez cette rubrique pour savoir comment vérifier si vous avez une licence en volume Skype Entreprise logiciels. 
  
Skype Room System utilise un client Skype Entreprise installé, qui nécessite une licence en volume logicielle. Avant de déployer le premier Skype Room System, découvrez l’état de la licence en volume du déploiement , à l’aide de serveurs de gestion de clés (KMS) ou de clés d’activation multiples (MAK).
  
## <a name="key-management-servers-kms"></a>Serveurs de gestion de clés (KMS)

Si KMS sont en place et distribuent Skype Entreprise activations de licence en volume, Skype Room System active automatiquement le client Skype Entreprise volume. Pour savoir si des KMS sont en place :
  
À partir d’une invite de commandes, exécutez :  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Pour configurer une KMS, voir KMS activation de [Office 2013](/previous-versions/office/office-2013-resource-kit/ee624357(v=office.15)) et de clés GVK pour l’activation KMS et Active Directory de [Office 2013](/DeployOffice/vlactivation/gvlks)
  
Office clé de licence en volume générique 2013 pour Lync : 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (cette clé amène Skype Room System à rechercher une KMS sur le réseau.)
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Clés d’activation multiples (MAK) à partir du Centre de service de licence en volume (VLSC)

Si le client utilise un autre logiciel de licence en volume, le service informatique gère les activations logicielles et le contrat de licence en volume (VLA) à l’aide du VLSC. Cela permettra également à l’entreprise d’acheter Skype Entreprise activations VL, après quoi elle peut obtenir une clé MAK pour l’entrée dans la console d’administration Skype Room System.
  
Un client ayant un VLA doit connaître ses informations d’identification VLSC, qui seront utilisées pour administrer le contrat et obtenir une mak. En cas de doute, le service financier du client doit être en mesure de confirmer si le client a payé un VLA.
  
Pour obtenir une clé MAK, accédez au Centre de gestion des licences en volume pour afficher les contrats et télécharger les clés de produit (MAK). Pour plus d’informations, voir le Centre de gestion des [licences en volume.](https://www.microsoft.com/Licensing/servicecenter/default.aspx) 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>MAK pour les Microsoft 365 ou Office 365 sans accès VLSC

Si le client n’a pas de contrat de licence en volume, les activations Skype Entreprise seront beaucoup plus difficiles à gérer. Toutefois, les Microsoft 365 et Office 365 qui n’ont pas accès au VLSC peuvent obtenir une mak promotionnelle en fournissant les informations suivantes au OEM qui vend le Skype Room System :
  
- Nom de la société
    
- Nom, adresse e-mail et numéro de téléphone du contact de déploiement
    
- Nombre de systèmes déployés
    
- Date de déploiement
    
- Si le client dispose d’un gestionnaire de compte technique Microsoft, le nom et les informations de contact du responsable technique de l’analyseur technique
