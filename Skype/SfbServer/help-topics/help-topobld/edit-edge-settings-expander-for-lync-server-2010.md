---
title: Modifier l’expanseur des paramètres de l’ordinateur Edge pour Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Pour modifier les paramètres du serveur Edge ou du pool de serveurs Edge, configurez les propriétés suivantes :'
ms.openlocfilehash: ab558edd16370d46d452f4e3d146dbf2153f3d9e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216115"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>Modifier l’expanseur des paramètres de l’ordinateur Edge pour Lync Server 2010
 
Pour modifier les paramètres du serveur Edge ou du pool de serveurs Edge, configurez les propriétés suivantes : 
  
 **Général**
  
- Nom de domaine **complet du pool interne**: le nom de domaine complet du pool interne est l’identité du serveur Edge ou du pool de serveurs Edge tel qu’il est défini dans l’enregistrement DNS (A ou AAAA pour IPv6) de l’hôte DNS.
    
- Sélectionnez **activer la Fédération pour ce pool Edge (port 5061)** si vous souhaitez activer le serveur Edge ou le pool de serveurs Edge pour la Fédération avec d’autres partenaires de protocole d’initiation de session.
    
    > [!IMPORTANT]
    > Vous ne pouvez définir qu’un seul serveur Edge ou pool de serveurs Edge activement pour la Fédération. La configuration illustrée dans la capture d’écran associée indique qu’un autre serveur Edge ou pool de serveurs Edge est déjà configuré pour la Fédération. L’enregistrement SRV DNS externe pour la Fédération (_sipfederationtls. _tcp. \<external domain name\> ) pointe vers le serveur Edge ou le pool de serveurs Edge pour la Fédération. 
  
- Le **port de réplication de configuration interne (https)**, par défaut sur le port TCP 4443, est le port que la copie locale (c’est-à-dire, locale vers les serveurs Edge) du magasin central de gestion est répliquée sur. La copie locale du magasin central de gestion se trouve dans la base de données **RTCLOCAL** du serveur SQL Server sur chaque ordinateur. La réplication est unidirectionnelle, initiée à partir du serveur de gestion centralisée (ou, le serveur frontal ou le pool frontal qui détient le rôle de serveur de gestion centralisée) vers les serveurs Edge et est un port d’interface interne.
    
  **Sélection du tronçon suivant**
  
- Sélectionnez dans la liste votre **Pool du tronçon suivant**. Vous définissez un directeur, un pool Directeur, un serveur frontal ou un pool frontal pour assumer ce rôle. Le pool de tronçon suivant est le serveur ou le pool de serveurs qui accepte les messages SIP entrants à partir de l’interface interne du serveur Edge ou du pool de serveur Edge et envoie le SIP sortant à l’interface interne du serveur Edge.
    
    > [!NOTE]
    > Le directeur est un rôle facultatif et si vous décidez de ne pas déployer les directeurs, les serveurs frontaux (ordinateur ou pool unique) assumeront le rôle de directeur. 
  
  **Paramètres externes**
  
Cette section des propriétés vous permet de modifier les propriétés des paramètres externes du serveur Edge ou du pool de serveurs Edge. Les propriétés suivantes peuvent être modifiées :
  
- Activez la case à cocher **activer un nom de domaine complet et une adresse IP distincts pour la conférence Web et A/V** si vous voulez affecter des adresses IP et des noms de domaine complets distincts à chaque service serveur Edge.
    
    > [!NOTE]
    > Si vous choisissez de ne pas activer la case à cocher, vous devez utiliser des ports distincts pour chaque service Edge. Chaque service Edge partagera le nom de domaine complet défini pour le service Edge d’accès et utilisera donc la même adresse IP. Chaque service Edge doit être identifié de manière unique soit par une adresse IP distincte et le même port, soit par la même adresse IP et des valeurs de port uniques. 
  
- Sélectionnez **NAT est activé pour le service Edge a/v** si vous voulez configurer le service Edge a/v pour qu’il utilise une adresse privée ou une autre adresse qui sera masquée derrière un périphérique de traduction d’adresses réseau (NAT).
    
- Pour modifier le **service Edge d’accès**, vous définissez le **nom de domaine complet du pool** pour le service Edge d’accès comme défini dans DNS par les enregistrements d’hôte (a et aaaa si IPv6 est utilisé) et une valeur de port
    
- Pour modifier le **service Edge de conférence Web**, vous définissez un **nom de domaine complet du pool** pour le service Edge de conférence Web comme défini dans DNS par les enregistrements d’hôte (a et aaaa si IPv6 est utilisé) et une valeur de port
    
- Pour modifier le **service Edge a/v**, vous définissez un **nom de domaine complet du pool** pour le service Edge a/v comme défini dans DNS par les enregistrements d’hôte (a et aaaa si IPv6 est utilisé) et une valeur de port
    
    > [!IMPORTANT]
    > Si vous avez activé la case à cocher **activer un nom de domaine complet et une adresse IP distincts pour les conférences Web et A/V** , seul le nom de domaine complet du pool de service Edge d’accès sera disponible pour modification. Assignez des ports distincts à chacun des trois services Edge.
  
  **OK** permet d’accepter et de valider les modifications de la boîte de dialogue.
  
  **Annuler** permet d’annuler les modifications et de fermer la boîte de dialogue.
  
  **Aide** permet d’afficher cet écran d’aide.
  

