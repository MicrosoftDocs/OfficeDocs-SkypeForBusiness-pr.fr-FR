---
title: Demande de certificat (autorité de certification)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
description: 'Lorsque vous faites une demande de certificat auprès d’une autorité de certification en ligne (généralement à des serveurs qui se trouvent sur votre réseau interne) dans la page Choisir une autorité de certification, vous avez le choix entre deux options :'
ms.openlocfilehash: 0081ab852a1650dfafd61471891a002be60def3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805324"
---
# <a name="certificate-request-certificate-authority"></a>Demande de certificat (autorité de certification)
 
Lorsque vous faites une demande de certificat auprès d’une autorité de certification en ligne (généralement à des serveurs qui se trouvent sur votre réseau interne) dans la page **Choisir une autorité de certification**, vous avez le choix entre deux options :
  
1. Sélectionner une autorité de certification dans une liste détectée pour votre environnement.
    
2. Indiquer une autre autorité de certification.
    
Si vous sélectionnez la première option, vous verrez une liste qui contient toutes les autorités de certification basées sur Windows Server détectées dans votre environnement. Sélectionnez l’autorité de certification adaptée à votre certificat. Il vous faudra peut-être consulter votre administrateur d’autorité de certification pour savoir quelle autorité de certification utiliser.
  
Si vous choisissez la deuxième option, entrez le nom de domaine complet (FQDN) et l’instance d’autorité de certification pour l’autorité de certification que vous utiliserez pour votre certificat. Cette option est appropriée si l’autorité de certification que vous souhaitez utiliser n’est pas basée sur Windows Server, mais qu’elle fonctionnera pour les autorités de certification basées sur Windows Server.
  
> [!IMPORTANT]
> Veillez à confirmer les appartenances aux groupes qui doivent fonctionner avec la demande de certificat. En règle générale, les autorisations requises par les autorités de certification sont différentes des exigences d’installation de Skype Entreprise Server sur les serveurs. Vérifiez les conditions requises pour effectuer la demande de certificat auprès de votre administrateur d‘autorité de certification. 
  

