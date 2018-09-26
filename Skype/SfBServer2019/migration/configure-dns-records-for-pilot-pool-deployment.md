---
title: Configuration des enregistrements DNS pour le déploiement d’un pool pilote
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Avant de déployer le pool pilote, vous devez mettre à jour les entrées d’hôte DNS A pour le pool pilote. Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Administrateurs du domaine ou un membre du groupe DnsAdmins.
ms.openlocfilehash: 13492f7972e127de7a8200a0dbe933c72aba2da7
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25029894"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Configuration des enregistrements DNS pour le déploiement d’un pool pilote

Avant de déployer le pool pilote, vous devez mettre à jour les entrées d’hôte DNS A pour le pool pilote. Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Administrateurs du domaine ou un membre du groupe DnsAdmins.
  
### <a name="to-configure-dns-host-a-records"></a>Pour configurer les enregistrements d’hôte DNS A

1. Sur le serveur de nom de domaine DNS (Domain Name System), cliquez sur **Démarrer**, sur **Outils d’administration**, puis cliquez sur **DNS**.
    
2. Dans l’arborescence de la console pour votre domaine, développez **Zones de recherche directes**, puis cliquez sur le domaine dans lequel Skype pour Business Server 2019 sera installé.
    
3. Cliquez sur **nouvel hôte (A ou AAAA)**.
    
4. Cliquez sur **nom**, tapez le nom d’hôte pour le Skype pour le pool d’entreprise Server 2019 (le nom de domaine est déterminée automatiquement à partir de la zone que l’enregistrement est défini dans et ne doit pas figurer dans le cadre de l’enregistrement A).
    
5. Cliquez sur **Adresse IP**, puis tapez l’adresse IP pour le pool frontal.
    
6. Cliquez sur **Ajouter un hôte**, puis cliquez sur **OK**. 
    
7. Lorsque vous avez terminé, cliquez sur **terminé**.
    

