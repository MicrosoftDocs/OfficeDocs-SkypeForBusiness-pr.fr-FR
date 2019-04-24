---
title: Modifier le développeur des paramètres de l’ordinateur Edge pour Lync Server 2010
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Vous modifiez les paramètres pour le serveur Edge ou le pool de serveurs Edge en configurant les propriétés suivantes :'
ms.openlocfilehash: a4ad88aa6ff565ac7c1ebb5134d476d34625418f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32203129"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>Modifier le développeur des paramètres de l’ordinateur Edge pour Lync Server 2010
 
Vous modifiez les paramètres pour le serveur Edge ou le pool de serveurs Edge en configurant les propriétés suivantes : 
  
 **Général**
  
- **Nom de domaine complet de pool interne**: le nom de domaine complet du pool interne est l’identité du serveur Edge ou du pool de serveurs Edge défini dans l’enregistrement d’hôte (A ou AAAA pour IPv6) domaine nom DNS (système).
    
- Sélectionnez **Activer la fédération pour ce pool Edge (port 5061)** si vous souhaitez activer le serveur Edge ou le pool de serveurs Edge pour la fédération avec d’autres partenaires de protocole de lancement de session.
    
    > [!IMPORTANT]
    > Vous ne pouvez définir un serveur Edge ou pool de serveurs Edge activement pour la fédération. La configuration indiquée dans la capture d’écran associé indique qu’un autre pool de serveur Edge ou Edge est déjà configuré pour la fédération. L’enregistrement SRV DNS pour la fédération (_sipfederationtls._tcp.\< nom de domaine externe\>) pointe vers le serveur Edge ou le pool de serveurs Edge pour la fédération. 
  
- Le **Port de réplication interne Configuration (HTTPS)**, par défaut sur le port TCP 4443, est le port que l’ordinateur local (autrement dit, local pour les serveurs de périphérie) copie du magasin Central de gestion est répliquée sur. La copie locale du magasin Central de gestion est dans la base de données **RTCLOCAL** dans SQL Server sur chaque ordinateur. La réplication est à sens unique, initiée à partir du serveur de gestion centralisée (ou, le pool frontal ou serveur frontal qui joue le rôle de serveur de gestion centralisée) pour les serveurs de périphérie et un port de l’interface interne.
    
  **Sélection du tronçon suivant**
  
- Pour la liste, sélectionnez le **pool du tronçon suivant**. Vous définissez le directeur, pool directeur, un pool frontal ou serveur frontal à ce rôle. Le pool du tronçon suivant est le serveur ou le pool de serveurs qui accepte les messages SIP entrantes à partir du serveur Edge ou interface interne du pool Edge et envoi sortant SIP à l’interface interne du serveur Edge.
    
    > [!NOTE]
    > Le directeur est un rôle facultatif et si vous décidez de ne pas déployer les directeurs, les serveurs frontaux (ordinateur unique ou pool) assumeront le rôle de directeur. 
  
  **Paramètres externes**
  
Cette section des propriétés vous permet de modifier des propriétés pour les paramètres du serveur Edge ou du pool de serveurs Edge externes. Les propriétés suivantes sont disponibles pour modifier :
  
- Sélectionnez le **Activer distinct nom de domaine complet et l’adresse IP pour les conférences web et A / V** des noms de case à cocher si vous souhaitez affecter des adresses IP distinctes et nom de domaine complet pour chaque service de serveur de transport Edge.
    
    > [!NOTE]
    > Si vous choisissez de n’activez ne pas la case à cocher, vous devez utiliser des ports distincts pour chaque service Edge. Chaque service Edge partage le nom de domaine complet défini pour le service Edge d’accès et par conséquent utiliseront la même adresse IP. Chaque service Edge doit être identifiée en une adresse IP distincte et même port, ou la même adresse IP et les valeurs de port unique. 
  
- Sélectionnez **A / V Edge service NAT activé** si vous souhaitez configurer A / V Edge de service à utiliser une adresse privée ou autre adresse sera masquée derrière un périphérique de traduction d’adresses réseau.
    
- Pour modifier le **service Edge d’accès**, vous définissez le **Nom complet du Pool** pour le service Edge d’accès tel que défini dans DNS par l’hôte (A et AAAA si IPv6 est utilisé) des enregistrements et une valeur de port
    
- Pour modifier le **service Edge de conférence Web**, vous définissez un **Nom complet du Pool** pour le service Edge de conférence Web tel que défini dans DNS par l’hôte (A et AAAA si IPv6 est utilisé) des enregistrements et une valeur de port
    
- Pour modifier la **A / service Edge v.**, vous définissez un **Nom complet du Pool** a / V Edge service tel que défini dans DNS par l’hôte (A et AAAA si IPv6 est utilisé) des enregistrements et une valeur de port
    
    > [!IMPORTANT]
    > Si vous avez sélectionné la **Activer distinct nom de domaine complet et l’adresse IP pour les conférences web et A / V** case à cocher, seul le service Edge d’accès nom complet du Pool sera disponible pour la modification. Affecter des ports distincts pour chacun des trois services de périphérie.
  
  **OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.
  
  **Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.
  
  **Aide** : permet d’afficher cet écran d’aide.
  

