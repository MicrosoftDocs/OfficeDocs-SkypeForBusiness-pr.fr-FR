---
title: 'Lync Server 2013 : Publication de la topologie'
TOCTitle: Publication de la topologie
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412935(v=OCS.15)
ms:contentKeyID: 49298735
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Publication de la topologie dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-08_

Chaque fois que vous utilisez le Générateur de topologie pour créer une topologie, vous devez publier cette dernière dans une base de données du magasin central de gestion afin que les données puissent servir au déploiement de Lync Server 2013. Procédez comme suit pour publier votre topologie.

## Pour publier la topologie

1.  Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.

2.  À partir du Générateur de topologie, dans l’arborescence de la console, cliquez avec le bouton droit sur **Lync 2013**, puis cliquez sur **Publier la topologie** .

3.  Dans la page **Bienvenue** de l’Assistant, cliquez sur **Suivant** .

4.  Dans la page **Le générateur de topologie a trouvé un magasin central de gestion** , cliquez sur **Suivant** .

5.  Dans la page **Créer d’autres bases de données** , cliquez sur **Suivant** .

6.  Dès que l’état indique que la base de données a été correctement créée, procédez comme suit :
    
      - Pour afficher le journal, cliquez sur **Afficher le journal** .
    
      - Pour fermer l’Assistant, cliquez sur **Terminer** .
        
        > [!IMPORTANT]  
        > S’il s’agit d’une nouvelle installation d’un serveur Edge ou d’un pool de serveurs Edge, vous devez exporter la configuration du serveur Edge d’un serveur frontal, pool de serveurs frontaux ou serveur Standard Edition existant. Pour exporter la configuration, reportez-vous à <a href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Exportation de la topologie Lync Server 2013 et copie vers le support externe de l’installation Edge</a>. Vous importez le fichier de configuration à partir du média externe ou d’un partage réseau lors de la phase d’installation et de déploiement des serveurs Edge via l’Assistant Déploiement de Lync Server.<br />
        Une fois que les serveurs Edge sont opérationnels et que la base de données du magasin local de gestion de la configuration est répliquée avec le déploiement interne, les mises à jour suivantes de la configuration de Lync Server 2013 seront publiées et répliquées sur les serveurs Edge.
