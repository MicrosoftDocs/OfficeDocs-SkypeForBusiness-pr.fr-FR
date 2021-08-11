---
title: Demande de certificat (autorité de certification)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
ROBOTS: NOINDEX, NOFOLLOW
description: 'Lorsque vous faites une demande de certificat auprès d’une autorité de certification en ligne (généralement à des serveurs qui se trouvent sur votre réseau interne) dans la page Choisir une autorité de certification, vous avez le choix entre deux options :'
ms.openlocfilehash: f6c0a52018c5741fab22f29e23dd1f8a27b3709cca347cd24bcc1c2e11b87688
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326480"
---
# <a name="certificate-request-certificate-authority"></a>Demande de certificat (autorité de certification)
 
Lorsque vous faites une demande de certificat auprès d’une autorité de certification en ligne (généralement à des serveurs qui se trouvent sur votre réseau interne) dans la page **Choisir une autorité de certification**, vous avez le choix entre deux options :
  
1. Sélectionner une autorité de certification dans une liste détectée pour votre environnement.
    
2. Indiquer une autre autorité de certification.
    
Si vous sélectionnez la première option, vous verrez une liste qui contient toutes les autorités de certification basées sur un serveur Windows détectées dans votre environnement. Sélectionnez l’autorité de certification adaptée à votre certificat. Il vous faudra peut-être consulter votre administrateur d’autorité de certification pour savoir quelle autorité de certification utiliser.
  
Si vous choisissez la deuxième option, entrez le nom de domaine complet (FQDN) et l’instance d’autorité de certification pour l’autorité de certification que vous utiliserez pour votre certificat. Cette option est appropriée si l’autorité de certification que vous souhaitez utiliser n’est pas basée sur Windows Server, mais qu’elle fonctionnera pour les autorités de certification basées sur Windows Server.
  
> [!IMPORTANT]
> Veillez à confirmer les appartenances aux groupes qui doivent fonctionner avec la demande de certificat. En règle générale, les autorisations requises par les autorités de certification sont différentes des exigences d’installation Skype Entreprise Server sur les serveurs. Vérifiez les conditions requises pour effectuer la demande de certificat auprès de votre administrateur d‘autorité de certification. 
  

