---
title: Configuration des enregistrements DNS pour le déploiement d’un pool pilote
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Avant de déployer le pool de pilotes, vous devez mettre à jour les entrées de l’hôte DNS pour le pool pilote. Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Domain Admins ou membre du groupe DnsAdmins.
ms.openlocfilehash: 3b8485564f3ea7f37a06b5c4d13c9450ba0a2694
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289622"
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
    

