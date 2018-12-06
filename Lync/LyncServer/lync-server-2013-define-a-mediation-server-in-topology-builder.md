---
title: "Lync Server 2013 : Déf. d’un serv. de médiation dans le générateur de topo."
TOCTitle: Définition d’un serveur de médiation dans le générateur de topologie
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398391(v=OCS.15)
ms:contentKeyID: 49297320
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition d’un serveur de médiation dans le générateur de topologie dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-03-25_

Suivez les étapes présentées dans cette rubrique pour utiliser le Générateur de topologie afin de définir un serveur de médiation autonome ou un pool colocalisé avec un pool de serveurs frontaux sur un site pour lequel vous n’avez pas précédemment déployé Voix Entreprise.

Vous pouvez définir une topologie à l’aide d’un compte qui est membre du groupe Administrateurs.

## Définir un serveur de médiation colocalisé sur un pool de serveurs frontaux

Suivez les étapes présentées dans cette rubrique pour utiliser le Générateur de topologie afin de définir un serveur de médiation colocalisé sur un pool de serveurs frontaux dans un site où Voix Entreprise n’a pas déjà été déployé.

## Pour ajouter un serveur de médiation à un pool de serveurs frontaux

1.  Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.

2.  Dans le Générateur de topologie, dans l’arborescence de la console, développez le nom du site pour lequel vous souhaitez définir un pool de serveurs frontaux.

3.  Dans l’arborescence de la console, cliquez avec le bouton droit sur le type de pool de serveurs frontaux souhaité, puis cliquez sur **Nouveau pool de serveurs frontaux**.

4.  Naviguez au sein de l’Assistant permettant de **Définir un nouveau pool frontal** jusqu’à ce que vous accédiez à la page **Sélectionner des rôles serveur colocalisés** .

5.  Dans **Sélectionner des rôles serveur colocalisés** , activez l’option **Colocaliser le serveur de médiation**.
    
    > [!NOTE]  
    > <ul>    
    > <li><p>Si le type de pool de serveurs frontaux sélectionné correspond à la version Enterprise Edition, le composant serveur de médiation est installé sur tous les serveurs frontaux de ce pool de serveurs frontaux.</p></li>    
    > <li><p>Le <strong>Pool du tronçon suivant</strong> utilisé par le serveur de médiation est le pool de serveurs frontaux sur lequel le serveur de médiation est colocalisé.</p></li>    
    > <li><p>Le <strong>Pool de serveurs Edge</strong> utilisé par le serveur de médiation correspond au pool de serveurs Edge associé au pool de serveurs frontaux sur lequel le serveur de médiation est colocalisé.</p></li>
    > </ul>


6.  Cliquez sur **Utiliser par défaut** pour utiliser ce pool de serveurs frontaux afin d’acheminer les appels de Microsoft Office Communications Server 2007 R2 vers le réseau téléphonique commuté.

7.  Cliquez sur **Terminer** quand vous avez terminé d’associer un ou plusieurs homologues au pool de serveurs frontaux.
    
    > [!NOTE]  
    > Avant de passer à l’étape suivante du processus de déploiement Voix Entreprise, assurez-vous que le pool de serveur de médiation (c’est-à-dire le pool de serveurs frontaux avec le composant serveur de médiation colocalisé) utilise les noms de domaine complets que vous avez spécifiés.

8.  Suivez ensuite les procédures décrites dans la section [Publication de la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md) de la documentation du Guide de déploiement pour ajouter le serveur de médiation à votre topologie avant de passer à la prochaine étape qui consiste à modifier les ports d’écoute du serveur de médiation, le cas échéant. Vous devez publier votre topologie chaque fois que vous utilisez le Générateur de topologie pour définir ou modifier votre topologie.

## Définir un serveur de médiation autonome

Suivez les étapes présentées dans cette rubrique pour utiliser le Générateur de topologie afin de définir un serveur de médiation autonome ou un pool dans un site où Voix Entreprise n’a pas déjà été déployé.

Si vous avez déjà déployé des serveurs de médiation colocalisés sur des pools de serveurs frontaux au niveau de ce site, vous pouvez ignorer cette section et [Installation des fichiers du serveur de médiation dans Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) avant de passer à [Configuration des jonctions dans Lync Server 2013](lync-server-2013-configuring-trunks.md).

> [!NOTE]  
> Dans cette section, nous partons du principe que vous avez déjà configuré au moins un pool de serveurs frontaux, comme indiqué dans <a href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Définition et configuration d’un pool frontal ou d’un serveur Standard Edition dans Lync Server 2013</a> et <a href="lync-server-2013-publish-the-topology.md">Publication de la topologie dans Lync Server 2013</a> au sein de la documentation du Guide de déploiement.

## Pour ajouter un serveur de médiation

1.  Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.

2.  Dans le Générateur de topologie, dans l’arborescence de la console, développez le nom du site pour lequel vous souhaitez définir un serveur de médiation.

3.  Dans l’arborescence de la console, cliquez avec le bouton droit sur le nœud **Pools de médiation** , puis cliquez sur **pool de serveurs de médiation**.

4.  Dans **Définir un nouveau pool de médiation** , tapez le nom de domaine complet du pool de serveur de médiation.

5.  Effectuez ensuite l’une des opérations suivantes :
    
      - Si vous souhaitez déployer plusieurs serveurs de médiation dans le pool afin de fournir la haute disponibilité, sélectionnez **Pool de plusieurs ordinateurs** .
        
        > [!NOTE]  
        > Vous devez déployer l’équilibrage de charge DNS pour prendre en charge les pools de serveur de médiation qui comportent plusieurs serveurs de médiation. Pour plus d’informations, reportez-vous à la section relative à l’utilisation de l’équilibrage de charge DNS sur les pools de serveur de médiation dans la rubrique <a href="lync-server-2013-dns-load-balancing.md">Équilibrage de charge DNS dans Lync Server 2013</a> de la documentation de planification.    
      - Si vous ne souhaitez déployer qu’un seul serveur de médiation dans le pool, car vous n’avez pas besoin de la haute disponibilité, sélectionnez **Pool d’un seul ordinateur** . Ignorez l’étape suivante.

6.  Si vous avez sélectionné **Pool de plusieurs ordinateurs** à l’étape précédente, dans l’élément **Définissez les ordinateurs inclus dans ce pool** , cliquez sur **Nom de domaine complet de l’ordinateur** , tapez le nom de domaine complet de chaque serveur présent dans le pool, puis cliquez sur **Ajouter** . Répétez cette étape pour tous les autres serveurs de médiation que vous souhaitez ajouter au pool. Une fois que vous avez défini tous les ordinateurs du pool, cliquez sur **Suivant** .

7.  Dans la page **Sélectionner le tronçon suivant** , cliquez sur **Pool du tronçon suivant** , cliquez sur le nom de domaine complet (FQDN) du pool frontal qui utilisera ce pool serveur de médiation, puis cliquez sur **Suivant** .

8.  Dans la page **Sélectionner un serveur Edge** , effectuez l’une des opérations suivantes :
    
      - Si vous souhaitez fournir une connectivité RTC aux utilisateurs externes pour lesquels Voix Entreprise est activé, sous **Sélectionnez le pool Edge utilisé par ce serveur de médiation** , cliquez sur le nom de domaine complet du pool de serveurs Edge qui utilisera ce pool serveur de médiation pour fournir la connectivité RTC aux utilisateurs externes, puis cliquez sur **Suivant** .
    
      - Si vous ne prévoyez pas d’activer Voix Entreprise pour les utilisateurs externes ou si vous ne souhaitez pas fournir la connectivité RTC aux utilisateurs quand ils se trouvent en dehors du réseau interne, cliquez sur **Suivant** .

9.  Suivez ensuite les procédures de la section [Publication de la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md) de la documentation de déploiement afin d’ajouter le serveur de médiation à la topologie. Vous devez publier votre topologie à chaque fois que vous utilisez le générateur de topologie pour créer ou modifier votre topologie afin que les données puissent être utilisées pour installer les fichiers des serveurs exécutant Lync Server. Effectuez ensuite les étapes suivantes afin de modifier si nécessaire les ports d’écoute du serveur de médiation.

## Définir les ports d’écoute du serveur de médiation

Suivez les étapes présentées dans cette rubrique pour utiliser le Générateur de topologie afin de définir les ports d’écoute utilisés par un serveur de médiation ou un pool pour accepter les connexions entrantes en provenance d’un homologue de passerelle.

## Pour modifier les ports d’écoute du serveur de médiation

1.  Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.

2.  Dans le Générateur de topologie, dans l’arborescence de la console, développez le nœud **Pools de médiation** , puis cliquez avec le bouton droit sur le serveur de médiation créé précédemment.

3.  Par défaut, les ports d’écoute SIP du serveur de médiation sont 5070 pour le trafic TLS provenant de Lync Server, 5067 pour le trafic TLS provenant des homologues (passerelles, PBX ou SBC). Le port TCP est désactivé par défaut. Vous devez activer le port TCP si vous disposez de passerelles qui ne prennent pas en charge le protocole TLS.

4.  Spécifiez la plage de ports d’écoute TLS ou TCP que le serveur de médiation doit utiliser pour accepter les connexions entrantes en provenance des passerelles RTC.
    
    > [!NOTE]  
    > L’entrée d’une plage de ports TCP n’est pas nécessaire, si l’option <strong>Activer le port TCP</strong> n’est pas activée. Ce paramètre est facultatif.

Vous devez ensuite [Définition d’une passerelle dans le générateur de topologie dans Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md), puis installer les fichiers sur chaque serveur de médiation du pool en respectant les procédures décrites dans [Installation des fichiers du serveur de médiation dans Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).

