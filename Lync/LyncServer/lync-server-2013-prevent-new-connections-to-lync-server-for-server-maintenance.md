---
title: "Blocage des nlles connexions à Lync Server lors de la maintenance du serveur "
TOCtitle: "Blocage des nlles connexions à Lync Server lors de la maintenance du serveur "
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg520964(v=OCS.15)
ms:contentKeyID: 49296501
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Blocage des nouvelles connexions à Lync Server lors de la maintenance du serveur

 

_**Dernière rubrique modifiée :** 2012-11-01_

Lync Server vous permet de mettre un serveur hors connexion (par exemple, pour des mises à niveau logicielles ou matérielles) sans risque de perte de service pour les utilisateurs. .

Quand vous spécifiez l’option qui empêche toute nouvelle connexion ou tout nouvel appel sur un serveur appartenant à un pool, Lync Server n’accepte plus de nouvelles connexions, ni de nouveaux appels une fois cette option implémentée. Quand un serveur empêche toute nouvelle connexion, il autorise ses sessions sur des connexions existantes à se poursuivre, jusqu’à ce qu’elles se terminent normalement. Une fois toutes les sessions existantes parvenues à terme, le serveur est prêt à être mis hors connexion.

Quand vous interdisez les nouvelles connexions sur un serveur frontal, certaines fonctionnalités et certains services Lync Server reposent sur la nouvelle fonctionnalité d’équilibrage de la charge DNS afin de garantir un bon fonctionnement. Si vous n’utilisez pas l’équilibrage de la charge DNS sur le pool, les connexions via ces services sont susceptibles de ne pas être réacheminées vers d’autres serveurs sur la période pendant laquelle le serveur interdit de nouvelles connexions. Ainsi, lors de la mise hors connexion du serveur, certaines sessions et certains appels peuvent être interrompus. Les fonctionnalités basées sur l’équilibrage de la charge DNS pour garantir que cette option fonctionne correctement sont les suivantes :

  - Intendant

  - application d’annonce de conférence

  - application Response Group

  - application d’annonce

  - application de parcage d’appel

Pour plus d’informations sur l’équilibrage de la charge DNS, voir [Équilibrage de charge DNS dans Lync Server 2013](lync-server-2013-dns-load-balancing.md) dans la documentation de planification.

En plus d’empêcher les nouvelles connexions pour tous les services d’un serveur exécutant Lync Server, vous pouvez aussi empêcher les nouvelles connexions pour les services Lync Server individuels. Par exemple, cette méthode est utile quand vous devez appliquer une mise à jour Lync Server qui ne nécessite pas d’arrêter l’intégralité du serveur. Notez que lorsque vous interdisez les connexions pour un service, vous devez sélectionner un service groupé et affiché dans la liste des services Windows. Par exemple, le service frontal Lync Server et l’agent de collecte des données de surveillance sont des services Lync Server distincts, mais dans la liste des services Windows, ils sont regroupés et apparaissent en tant que service frontal Lync Server. Vous pouvez empêcher les nouvelles connexions pour le service frontal Lync Server, mais vous ne pouvez pas les empêcher séparément pour ces deux services Lync Server individuels sous-jacents.

> [!IMPORTANT]  
> Lorsque vous configurez un serveur pour empêcher les nouvelles connexions, puis le redémarrez, par défaut, le serveur accepte immédiatement les connexions. Si vous ne voulez pas que cela se produise, configurez le serveur pour qu’il ne soit suspendu et redémarré que manuellement avant de redémarrer le serveur.

## Pour empêcher les nouvelles connexions à Lync Server:

1.  Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.

2.  Ouvrez la console du composant logiciel enfichable des services : Cliquez sur **Démarrer**, pointez sur **Tous les programmes** et sur **Outils d’administration**, puis cliquez sur **Services**.

3.  Dans la liste, double-cliquez sur le service Windows Lync Server auquel vous voulez empêcher les nouvelles connexions.

4.  Dans la boîte de dialogue Propriétés, sous **État du service : Démarré**, cliquez sur **Suspendre**.

5.  La méthode facultative et recommandée consiste à cliquer sur **Manuel**, en regard de **Type de démarrage**.
    
    > [!IMPORTANT]  
    > Quand vous configurez un serveur de manière à empêcher de nouvelles connexions puis que vous le redémarrez, par défaut, le serveur accepte immédiatement les nouvelles connexions après son redémarrage. Pour éviter cela, configurez le serveur de manière à ce qu’il s’interrompe et reprenne uniquement manuellement, puis redémarrez-le.

6.  Lorsque vous avez terminé, cliquez sur **OK**.

