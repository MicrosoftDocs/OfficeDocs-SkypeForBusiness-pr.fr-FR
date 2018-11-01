---
title: 'Lync Server 2013 : Configuration logicielle requise pour Entreprise Voix'
TOCTitle: Configuration logicielle requise pour Entreprise Voix
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425916(v=OCS.15)
ms:contentKeyID: 49297006
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration logicielle requise pour Entreprise Voix dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-03_

Vérifiez que l’infrastructure dans laquelle vous souhaitez déployer Voix Entreprise respecte les conditions préalables logicielles suivantes :

  - Lync Server 2013 Standard Edition ou Enterprise Edition est installé et opérationnel sur votre réseau.

  - Tous les serveurs Edge sont déployés et opérationnels dans votre réseau de périmètre, dont les serveurs Edge exécutant le service Edge d’accès, le service Edge A/V, le service Edge de conférence web et un proxy inverse.

  - Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 ou Microsoft Exchange Server 2013 est requis pour l’intégration de la messagerie unifiée Exchange à Lync Server et pour fournir des notifications enrichies et des informations de journal d’appels aux points de terminaison Lync.

  - Un ou plusieurs utilisateurs ont été créés et activés pour Lync Server.

  - Les clients et périphériques Lync ont été correctement déployés.

  - Le Générateur de topologie est installé sur un serveur de votre réseau.

## Étapes suivantes : Vérifier les conditions préalables de sécurité et de configuration

Une fois que vous avez vérifié les conditions préalables logicielles pour Voix Entreprise, vous pouvez utiliser la documentation pour poursuivre la préparation du déploiement de Voix Entreprise :

1.  Vérifiez les conditions préalables matérielles, de sécurité et de configuration utilisateur, comme indiqué dans [Conditions prérequises de configuration et de sécurité pour Voix Entreprise dans Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).

2.  Installez le serveur de médiation comme indiqué dans [Installation des fichiers du serveur de médiation dans Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), mais *uniquement* si vous souhaitez déployer un pool ou un serveur de médiation autonome, puisque les serveurs de médiation sont installés dans le cadre du processus de déploiement du pool frontal ou du serveur Standard Edition en cas de colocalisation.

3.  Configurez les connexions de jonction pour fournir une connectivité RTC aux utilisateurs, comme spécifié dans [Configuration des jonctions dans Lync Server 2013](lync-server-2013-configuring-trunks.md).

