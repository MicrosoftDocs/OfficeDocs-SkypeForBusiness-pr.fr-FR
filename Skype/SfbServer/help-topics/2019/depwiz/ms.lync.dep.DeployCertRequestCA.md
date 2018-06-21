---
title: Demande de certificat (autorité de certification)
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
description: 'Lors d’une demande de certificat à une autorité de certification en ligne (CA) (en règle générale, ce sont les serveurs qui se trouvent sur votre réseau interne) sur la page Choisissez une autorité de Certification (CA), vous avez deux options :'
ms.openlocfilehash: 0092e29f7cb477686cb873aa7318519d12381f72
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/20/2018
ms.locfileid: "19973114"
---
# <a name="certificate-request-certificate-authority"></a>Demande de certificat (autorité de certification)
 
Lorsque vous faites une demande de certificat auprès d’une autorité de certification en ligne (généralement à des serveurs qui se trouvent sur votre réseau interne) dans la page **Choisir une autorité de certification**, vous avez le choix entre deux options :
  
1. Sélectionner une autorité de certification dans une liste détectée pour votre environnement.
    
2. Indiquer une autre autorité de certification.
    
Si vous sélectionnez la première option, vous verrez une liste déroulante qui contient toutes les autorités de certification basée sur Windows Server sont détectées dans votre environnement. Sélectionnez l’autorité de certification adaptée à votre certificat. Il vous faudra peut-être consulter votre administrateur d’autorité de certification pour savoir quelle autorité de certification utiliser.
  
Si vous choisissez la deuxième option, entrez le nom de domaine complet (FQDN) et l’instance d’autorité de certification pour l’autorité de certification que vous utiliserez pour votre certificat. Cette option est appropriée si l’autorité de certification que vous souhaitez utiliser n’est pas basée sur Windows Server, mais qu’elle fonctionnera pour les autorités de certification basées sur Windows Server.
  
> [!IMPORTANT]
> Veillez à confirmer les appartenances aux groupes qui doivent fonctionner avec la demande de certificat. En règle générale, les autorités de certification ont une demande d’autorisation différentes à partir de la configuration requise pour l’installation de Skype pour Business Server sur les serveurs. Vérifiez les conditions requises pour effectuer la demande de certificat auprès de votre administrateur d’autorité de certification. 
  

