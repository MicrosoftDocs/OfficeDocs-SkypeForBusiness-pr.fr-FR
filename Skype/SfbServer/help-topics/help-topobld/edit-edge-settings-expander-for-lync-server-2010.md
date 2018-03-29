---
title: Modifier l’agrandissement de paramètres de bord pour Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Vous modifiez les paramètres pour le serveur de transport Edge ou le pool de bord en configurant les propriétés suivantes :'
ms.openlocfilehash: 682412e1a486cc7351f081d903d8db1131367623
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>Modifier l’agrandissement de paramètres de bord pour Lync Server 2010
 
Vous modifiez les paramètres pour le serveur de transport Edge ou le pool de bord en configurant les propriétés suivantes : 
  
 **Général**
  
- **Nom de domaine complet de pool interne**: le nom de domaine complet du pool interne est l’identité du serveur de transport Edge ou pool de bord tel que défini dans l’enregistrement d’hôte (A ou AAAA pour IPv6) domaine nom système (DNS).
    
- Sélectionnez **Activer la fédération pour ce pool de bord (le port 5061)** si vous souhaitez activer le serveur de transport Edge ou le pool de bord pour la fédération avec d’autres partenaires de protocole de lancement de session.
    
    > [!IMPORTANT]
    > Vous ne pouvez définir qu’un serveur de transport Edge ou pool de bord activement pour la fédération. La configuration illustrée dans la capture d’écran associé indique qu’un autre pool de serveur de transport Edge ou Edge est déjà configuré pour la fédération. L’enregistrement DNS SRV externe pour la fédération (_sipfederationtls._tcp.\< nom de domaine externe\>) pointe vers le serveur de transport Edge ou le pool de bord pour la fédération. 
  
- Le **Port de réplication interne Configuration (HTTPS)**, par défaut sur le port TCP 4443, est le port qui local (c'est-à-dire local sur les serveurs Edge) copie du magasin Central de gestion est répliquée sur. La copie locale du magasin Central de gestion se trouve dans la base de données **RTCLOCAL** dans le SQL Server sur chaque ordinateur. La réplication est à sens unique, initiée à partir du serveur d’administration centrale (ou, le pool de Front-End ou de serveur frontal qui détient le rôle de serveur de gestion Central) vers les serveurs Edge et est un port de l’interface interne.
    
 **Sélection de saut suivante**
  
- Pour la liste, sélectionnez le **pool du tronçon suivant**. Vous définissez soit un directeur, directeur pool, pool de Front-End ou de serveur frontal pour assumer ce rôle. Le pool du tronçon suivant est le serveur ou le pool de serveur qui accepte les messages entrants de SIP du serveur Edge ou interface de bord pool interne et envoi sortant SIP vers l’interface interne du bord.
    
    > [!NOTE]
    > Le directeur est un rôle facultatif et si vous décidez de ne pas déployer les directeurs, les serveurs frontaux (ordinateur unique ou pool) suppose que le rôle de directeur. 
  
 **Paramètres externes**
  
Cette section de propriétés vous permet de modifier les propriétés des paramètres du serveur Edge ou pool de bord externes. Les propriétés suivantes sont disponibles pour modifier :
  
- Sélectionnez le **Activer distinct nom de domaine complet et l’adresse IP pour les conférences web et A / V** noms de case à cocher si vous souhaitez affecter des adresses IP distinctes et domaine pleinement qualifié à chaque service de serveur de transport Edge.
    
    > [!NOTE]
    > Si vous choisissez pour ne pas sélectionner la case à cocher, vous devez utiliser des ports distincts pour chaque service de bord. Chaque service de bord partage le nom de domaine complet défini pour le service Edge d’accès et par conséquent utilise la même adresse IP. Chaque service de bord doit être identifié de manière unique en une adresse IP distincte et même port, ou la même adresse IP et les valeurs de port unique. 
  
- Sélectionnez **A / V Edge service NAT activé** si vous souhaitez configurer l’A / V Edge service d’utiliser une adresse privée ou autres adresses qui seront masquées derrière un périphérique de traduction d’adresses réseau.
    
- Pour modifier le **service Edge d’accès**, vous définissez le **Nom FQDN du Pool** pour le service Edge d’accès tel que défini dans le système DNS par hôte (AAAA si IPv6 est utilisé et A) les enregistrements et une valeur de port
    
- Pour modifier le **serveur Edge de conférence Web service**, vous définissez un **Pool de nom de domaine complet** pour le service serveur Edge de conférence Web tel que défini dans le système DNS par hôte (AAAA si IPv6 est utilisé et A) les enregistrements et une valeur de port
    
- Pour modifier la **A / V Edge service**, vous définissez un **Nom de domaine complet Pool** pour l’un / V Edge service tel que défini dans le système DNS par hôte (AAAA si IPv6 est utilisé et A) enregistrements et une valeur de port
    
    > [!IMPORTANT]
    > Si vous avez sélectionné la **Activer distinct nom de domaine complet et l’adresse IP pour les conférences web et A / V** case à cocher, seul le service Edge d’accès FQDN du Pool seront disponible pour l’édition. Affecter des ports distincts pour chacun des trois services Edge.
  
 **OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.
  
 **Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.
  
 **Aide** : permet d’afficher cet écran d’aide.
  

