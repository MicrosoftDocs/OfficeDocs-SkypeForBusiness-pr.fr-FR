---
title: Mettre à jour les enregistrements SRV DNS
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Administrateurs du domaine ou un membre du groupe DnsAdmins.
ms.openlocfilehash: 5cdf98d065abbb57b3cb654c8b770f8f1f87500c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30872723"
---
# <a name="update-dns-srv-records"></a>Mettre à jour les enregistrements SRV DNS

Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Administrateurs du domaine ou un membre du groupe DnsAdmins.
  
Cette rubrique décrit comment mettre à jour les enregistrements de nom de domaine DNS (Domain Name System) après la migration vers Skype pour Business Server 2019. Une fois que tous les utilisateurs ont été déplacés vers Skype pour Business Server 2019, mais avant que le pool hérité ou un directeur est désactivé, vous devez mettre à jour les enregistrements DNS SRV dans votre DNS interne pour chaque domaine SIP. Cette procédure suppose que votre serveur DNS interne comporte des zones pour vos domaines utilisateur SIP.
  
## <a name="to-configure-a-dns-srv-record"></a>Pour configurer un enregistrement DNS SRV

1. Sur le serveur DNS, cliquez sur **Démarrer**, sur **Outils d’administration**, puis cliquez sur **DNS**.
    
2. Dans l’arborescence de la console pour votre domaine SIP, développez **Zones de recherche directes**, développez le domaine SIP dans le Skype pour Business Server 2019 est installé, puis accédez au paramètre **_tcp** . 
    
3. Dans le volet droit, cliquez sur **_sipinternaltls** et sélectionnez **Propriétés**.
    
4. Dans **hôte offrant ce service**, mettez à jour le nom de domaine complet pour pointer vers le Skype pour le pool d’entreprise Server 2019 hôte.
    
5. Cliquez sur **OK**.
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Pour vérifier que le nom de domaine complet du pool frontal ou serveur Standard Edition server peut être résolu

1. Ouvrez une session un ordinateur client du domaine.
    
2. Cliquez sur **Démarrer **, puis sur **Exécuter **.
    
3. Dans la zone **Ouvrir** , tapez cmd, puis cliquez sur **OK**.
    
4. À l’invite de commandes, tapez nslookup _ \<nom de domaine complet du pool frontal\> _ ou _ \<nom de domaine complet du serveur Standard Edition\>_, puis appuyez sur ENTRÉE.
    
5. Vérifiez que vous recevez une réponse qui est résolu en adresse IP appropriée pour le nom de domaine complet.
    

