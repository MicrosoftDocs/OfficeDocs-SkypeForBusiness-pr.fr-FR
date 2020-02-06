---
title: Configuration des enregistrements DNS pour le déploiement d’un pool pilote
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Avant de déployer le pool de pilotes, vous devez mettre à jour les entrées de l’hôte DNS pour le pool pilote. Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Domain Admins ou membre du groupe DnsAdmins.
ms.openlocfilehash: 94e5047dc82b0ddb55b03ad5c466011878c05ae7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813852"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Configuration des enregistrements DNS pour le déploiement d’un pool pilote

Avant de déployer le pool de pilotes, vous devez mettre à jour les entrées de l’hôte DNS pour le pool pilote. Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Domain Admins ou membre du groupe DnsAdmins.
  
### <a name="to-configure-dns-host-a-records"></a>Pour configurer les enregistrements d’un hôte DNS

1. Sur le serveur DNS (Domain Name System), cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.
    
2. Dans l’arborescence de la console pour votre domaine, développez **zones de recherche directe**, puis cliquez avec le bouton droit sur le domaine dans lequel Skype entreprise Server 2019 sera installé.
    
3. Cliquez sur **nouvel hôte (A ou AAAA)**.
    
4. Cliquez sur **nom**, entrez le nom d’hôte du pool 2019 de Skype entreprise Server (le nom de domaine est utilisé dans la zone dans laquelle l’enregistrement est défini et n’a pas besoin d’être entré dans le cadre de l’enregistrement a).
    
5. Cliquez sur **adresse IP**, puis tapez l’adresse IP de la liste frontale.
    
6. Cliquez sur **Ajouter un hôte**, puis cliquez sur **OK**. 
    
7. Lorsque vous avez terminé, cliquez sur **terminé**.
    

