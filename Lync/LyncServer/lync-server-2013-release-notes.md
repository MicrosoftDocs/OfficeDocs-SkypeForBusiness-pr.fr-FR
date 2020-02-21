---
title: Notes de publication de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f572c120d86c5f89fb82e23066a6262e957e5e2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="release-notes-for-lync-server-2013"></a>Notes de publication pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-12-08_

Bienvenue dans les notes de publication de Lync Server 2013. Consultez ce fichier pour obtenir des informations sur les problèmes connus concernant Lync Server 2013.

<div>

## <a name="about-this-document"></a>À propos de ce document

Ce document contient des informations importantes que vous devez savoir avant de déployer et d’utiliser Lync Server 2013. Pour plus d’informations sur Lync Server 2013, reportez-vous à la documentation de [Microsoft Lync Server 2013](microsoft-lync-server-2013.md) .

Ce document contient les sections suivantes :

  - Client Lync 2013

  - Lync Server

  - Installation

  - Mobilité

  - Vidéoconférence

  - Voix Entreprise

  - Présence

  - Application Response Group et application Parcage d’appel

  - Panneau de configuration de Lync Server, Générateur de topologie et Outil de planification

  - Localisation

  - Copyright

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a>Client Lync 2013

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a>Le transfert d’un fichier dans un message instantané échoue si le fichier est ouvert dans une autre application

**Exécuter**

Si vous tentez de transférer un fichier, tel qu’un document Word, en l’incluant dans un message instantané à un autre utilisateur Lync, le transfert semble réussi, mais il est possible que le transfert du fichier échoue. Une icône pour le type de fichier s’affiche dans le client Lync, mais le fichier ne peut pas être ouvert par le destinataire prévu. Aucun message d’erreur ne s’affiche pour vous informer que le transfert a échoué.

**Palliatives**

Pour contourner ce problème, fermez le fichier ou l’application ouvert qui s’est ouvert avant de tenter de transférer le fichier dans un message instantané.

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a>Lync Server

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a>Si la réplication de données du service de stockage Lync Server échoue, les administrateurs devront vérifier les compteurs de performances pour les éléments de file d’attente du service de stockage périmés.

**Exécuter**

Le service de stockage Lync Server utilise Windows fabric pour la réplication. Si les données sont supprimées sur un serveur frontal principal, mais que la suppression sur un serveur frontal secondaire échoue, par exemple, en cas d’arrêt inattendu ou d’erreur sur le serveur frontal, les données peuvent être conservées et orphelines. Ces données orphelines peuvent entraîner une dégradation des performances et un gaspillage de l’espace disque.

**Palliatives**

Pour contourner ce problème, si l’espace de\_la\_base\_de\_données LYSS DB utilisé (ID = 32058\_)\_et\_LYSS\_DB utilisés (ID = 32059) sont générés dans le journal des événements, les administrateurs doivent vérifier le compteur de performances sur le serveur frontal sous **ls : LYSS-API de service de stockage** avec le nom **LYSS-nombre actuel d’éléments de file d’attente obsolètes**. Si ce compteur de performance a une valeur élevée (par exemple, supérieure à 50000), l’administrateur doit exécuter l’outil CleanuUpStorageServiceData. exe dans le kit de ressources Lync Server 2013, ce qui supprime toutes les données orphelines du pool. Pour plus d’informations sur l’outil, voir la documentation du kit de ressources Lync Server 2013.

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a>Chaque fois que la configuration de l’adresse IP d’un serveur ou d’un pool est modifiée, les services Lync Server doivent être redémarrés.

**Exécuter**

Lorsque la configuration de l’adresse IP est modifiée pour un déploiement Lync Server 2013, par exemple en passant d’IPv4 à double pile ou de double pile en IPv6, tous les composants serveur ne prennent pas en charge la modification de la configuration avant le redémarrage des services.

**Palliatives**

Pour contourner ce problème, redémarrez les services Lync Server après avoir modifié la configuration d’adresse IP pour le déploiement. Pour ce faire, exécutez les applets de commande suivantes dans Lync Server Management Shell :

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a>L’applet de commande de transaction synthétique de conférence rendez-vous n’est plus disponible dans le pack d’administration Lync Server 2013

**Exécuter**

La cmdlet de transaction synthétique de conférence rendez **-vous-CsDialInConferencing** n’est plus disponible dans le pack d’administration Lync Server 2013.

**Palliatives**

L’utilisation de l’applet de commande de transaction synthétique de conférence rendez-vous **Test-CsDialInConferencing** est prise en charge uniquement en interne, au sein d’une entreprise.

Les administrateurs peuvent continuer à utiliser la cmdlet dans Lync Server Management Shell à des fins de résolution des problèmes. Si nécessaire, une entreprise peut développer un pack de gestion privé pour exécuter l’applet de commande en interne.

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a>Le service de journalisation centralisée cesse si le trafic réseau est perturbé lorsque les fichiers journaux sont copiés sur le partage réseau

**Exécuter**

Lorsque le service de journalisation centralisée est configuré de façon à utiliser un chemin d’accès réseau (la valeur du paramètre CacheFileNetworkFolder de l’applet de commande **Get-CsClsConfiguration** est un chemin d’accès UNC valide), les fichiers journaux mis en cache sont copiés vers le partage réseau. Si le trafic réseau est perturbé durant la copie des fichiers, une exception se produit et le service de journalisation centralisée est arrêté.

Ce service étant configuré de façon à redémarrer automatiquement jusqu’à trois fois, il récupèrera suite aux trois premières exceptions.

**Palliatives**

Il n’existe aucune solution de contournement à ce problème. Pour identifier le problème, surveillez le journal des événements pour l’ID d’événement 7031 à partir du « gestionnaire de contrôle des services » qui se connecte lorsque le service « Lync Server Centralized Logging Service agent » s’est terminé de manière inattendue. Si cela se produit plus de trois fois, redémarrez manuellement le service à l’aide de l’applet de commande **Start-CsWindowService**.

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a>Les éléments de file d’attente du service de stockage doivent être importés manuellement

**Exécuter**

Lync Server 2013 stocke des données sur les conférences et la messagerie instantanée, telles que les messages archivés et l’enregistrement des détails des appels, sur une base de données sur chaque serveur frontal. Les données sont stockées dans la base de données lorsqu’elles sont traitées avant d’être remises à la destination prévue. Pour améliorer les performances, Lync Server 2013 exporte régulièrement les éléments de la file d’attente à partir de la base de données locale qui ne sont pas traités pendant une longue période, et les enregistre sur le magasin de fichiers. Si le magasin de fichiers n’est pas disponible, les éléments sont stockés sur chaque serveur frontal. La même opération se produit afin d’éviter toute perte de données durant le basculement de pool.

Pendant l’opération d’exportation, le service de stockage Lync Server enregistre toutes les étapes dans le journal des événements avec les ID d’événement 32075 (l’opération de vidage complet est démarrée), 32076 (vidage total terminé), 32082 (le vidage du niveau de maintenance est démarré), 32083 (vidage au niveau de la maintenance est terminé), 32089 (vidage effectué en raison du remplissage de la base de données). Ces données ne seront pas automatiquement importées sur le système pour être traitées et livrées à leur destination finale (SQL Server ou Exchange Server).

**Palliatives**

Pour importer les données dans le système, les administrateurs doivent utiliser l’outil ImportStorageServiceData dans le kit de ressources Lync Server, qui rajoutera les données au système pour qu’elles soient traitées et livrées à leur destination finale.

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a>Les recherches de requête sur le Web du carnet d’adresses échouent si la valeur par défaut de UseNormalizationRules est remplacée par false.

**Exécuter**

Si la valeur par défaut de UseNormalizationRules est changée en False, les recherches d’interrogation web du carnet d’adresses échouent. Une fois la valeur par défaut modifiée, les utilisateurs du client Lync ne pourront pas utiliser l’interrogation web du carnet d’adresses Lync pour rechercher des utilisateurs.

**Palliatives**

Si la valeur par défaut de UseNormalizationRules est définie sur false afin que les utilisateurs puissent utiliser des numéros de téléphone tels que définis dans les services de domaine Active Directory sans Lync Server 2013 appliquant des règles de normalisation, contourner ce problème en procédant comme suit :

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Effectuez l’une des opérations suivantes :
    
      - Si votre déploiement inclut uniquement des serveurs Lync Server 2013, exécutez l’applet de commande suivante au niveau global pour modifier les valeurs de UseNormalizationRules et IgnoreGenericRules sur true :
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Si votre déploiement inclut une combinaison de Lync Server 2013 et Lync Server 2010 ou Office Communications Server 2007 R2, exécutez l’applet de commande suivante et affectez-la à chaque pool Lync Server 2013 dans la topologie :
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  Attendez que le réplication CMS ait lieu sur tous les pools.

4.  Modifiez le fichier de règles de normalisation téléphonique de votre déploiement afin d’effacer le contenu. Le fichier se trouve sur le partage de fichiers de chaque pool Lync Server 2013. Si le fichier n’est pas présent, créez un fichier vide nommé « Company\_Phone\_Number\_Normalization\_Rules. txt ».

5.  Attendez quelques minutes que tous les pools frontaux aient lu les nouveaux fichiers.

6.  Exécutez l’applet de commande suivante sur chaque pool Lync Server 2013 de votre déploiement.
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a>L’événement d’erreur de serveur de carnet d’adresses 21054 est généré une fois par jour pour chaque pool Lync 2013

**Exécuter**

Le serveur de carnet d’adresses Lync Server 2013 générera un événement d’erreur 21054 une fois par jour lors de la maintenance quotidienne. L’erreur est également générée chaque fois qu’un administrateur exécute la cmdlet **Update-csAddressBook** , même si la mise à jour réussit. Toutefois, cet événement d’erreur peut être ignoré lorsque la mise à jour réussit.

**Palliatives**

Lorsque vous rencontrez cet événement d’erreur, exécutez l’applet de commande suivante :

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

Si l’applet de commande signale qu’il n’y a pas d’objets non indexés ou abandonnés, l’événement d’erreur 21054 peut être ignoré en toute sécurité.

Par ailleurs, l’indicateur d’intégrité de clé « Utilisateurs de carnet d’adresses correctement indexés » doit être désactivé dans System Center Operations Manager.

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a>Les demandes peuvent échouer lorsque le protocole IPv6 est configuré sur un pool de serveurs Edge

**Exécuter**

Lorsque le protocole IPv6 est configuré sur un pool Edge, certaines demandes envoyées au pool Edge peuvent échouer.

**Palliatives**

Pour contourner ce problème, ne configurez pas de pool Edge avec le protocole IPv6.

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a>La cmdlet Invoke-applet cspoolfailback peut échouer pendant la restauration automatique du pool

**Exécuter**

Lors d’une tentative de restauration de pool, l’applet de commande **invoke-csPoolFailback** peut échouer et renvoyer l’erreur « Désolé... En dépit de plusieurs tentatives, nous n’avons pas pu effectuer le processus d’hydration. ».

**Palliatives**

Pour contourner ce problème, réexécutez l’applet de commande et attendez qu’elle réussisse. Notez que le processus de restauration peut prendre plusieurs minutes (jusqu’à 60 minutes pour un pool de 20 000 utilisateurs).

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a>Une perte de données peut se produire lorsque vous ajoutez un serveur frontal à un pool déjà établi-hybride, Skype entreprise Online

**Exécuter**

Vous pouvez rencontrer ce problème dans un environnement où un pool comporte plusieurs serveurs frontaux, et vous devez redémarrer l’un des serveurs frontaux ou ajouter un nouveau serveur frontal qui ne faisait pas partie du pool.

Les utilisateurs dont les données sont en cours d’archivage peuvent constater une perte de données jusqu’à ce qu’une distribution stable de l’archivage des données soit établie pour le pool. Cette période de perte de données potentielle est limitée à 15 minutes pour les conversations de personne à personne et à 30 minutes pour les conférences.

**Palliatives**

Lorsque vous effectuez une maintenance au lieu de démarrer les serveurs frontaux dans le pool un par un, vous devez basculer le pool vers un autre pool, puis effectuer les tâches de maintenance sur les serveurs. Vous pouvez également rendre le service indisponible avant d’effectuer les tâches de maintenance, puis rétablir la disponibilité une fois la maintenance terminée.

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a>Les administrateurs ne peuvent pas obtenir le nombre de licenciés à l’aide de la cmdlet Get-applet csclientaccesslicense

**Exécuter**

Les administrateurs ne peuvent pas obtenir d’informations correctes relatives à l’utilisation des licences client à l’aide de l’applet de commande **Get-CsClientAccessLicense**.

**Palliatives**

Pour vérifier le type de licence serveur, vous pouvez exécuter l’applet de commande **Get-CsService** pour extraire les noms de domaine complets de toutes les bases de données. Si le nom de domaine complet du serveur frontal est identique au nom de domaine complet de la base de données principale, la licence est une licence Standard Edition. Dans le cas contraire, il s’agit d’une licence Enterprise Edition.

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a>Le nombre de licenciés client n’est pas correctement signalé

**Exécuter**

Lors de la détermination du nombre de licences client, vous pouvez rencontrer les conditions suivantes :

1.  **Nombre de licences incorrect pour les utilisateurs mobiles**
    
    Le nombre de licences est basé sur le nombre d’adresses IP uniques pour les utilisateurs de périphériques mobiles. Le nombre de licence sera limité des manières suivantes :
    
      - Le nombre de licences est surévalué si l’adresse IP de l’utilisateur change durant les sessions Lync. Cela peut se produire lorsqu’un utilisateur se connecte à Lync Server à partir de plusieurs emplacements à l’aide d’un client de bureau.
    
      - Le nombre de licences est sous-évalué si un utilisateur se connecte avec un client mobile, car l’adresse IP de l’appareil ne peut pas être déterminée.

2.  **Les licences sont comptabilisées deux fois pour les appels PSTN (Public Switched Telephone Network) vers le client Lync, les appels de clients Lync vers des lignes PSTN et les appels Lync transférés à des lignes PSTN**
    
    Dans les scénarios suivants, deux licences supplémentaires sont comptabilisées (au lieu d’une seule) car le numéro de téléphone et l’utilisateur Lync sont tous deux comptés afin de déterminer le nombre de licences utilisés. Pour obtenir des données de licence correctes, supprimez manuellement les licences générées par un numéro de téléphone.
    
      - Un appel téléphonique PSTN vers Lync
    
      - Un appel Lync vers une ligne PSTN
    
      - Un appel PSTN vers Lync, qui est ensuite transféré par Lync à une ligne PSTN. L’une des lignes PSTN est comptabilisée.

3.  **Aucune licence n’est comptabilisée pour un téléphone Lync connecté**
    
    Lorsqu’un utilisateur utilise un téléphone certifié Lync, si le téléphone se connecte et reste connecté (auquel cas son statut de connexion est conservé), le téléphone n’est pas comptabilisé comme utilisant une licence si l’interrogation de licence a lieu après la connexion du téléphone.

4.  **Licences comptabilisées pour les téléphones PSTN prenant part à des conférences**
    
    Lorsqu’un utilisateur prend part à une conférence avec un téléphone PSTN, une licence est comptabilisée de manière incorrecte pour la participation à la conférence. Toutefois, aucune licence n’est nécessaire pour prendre part à une conférence avec un téléphone PSTN.

**Palliatives**

1.  **Nombre de licences incorrect pour les utilisateurs mobiles**
    
      - Vous pouvez identifier manuellement les adresses IP qui appartiennent au même périphérique, puis supprimer l’une d’entre elles dans le nombre de licences.
    
      - Il n’existe aucune solution de contournement à ce problème dans le cas des appareils mobiles se connectant avec le client Lync.

2.  **Les licences sont comptabilisées deux fois pour les appels PSTN vers le client Lync, les appels de clients Lync vers des lignes PSTN et les appels Lync transférés à des lignes PSTN**
    
    Vous devez identifier manuellement le numéro de téléphone PSTN et supprimer la licence générée pour ce numéro.

3.  **Aucune licence n’est comptabilisée pour un téléphone Lync connecté**
    
    Vous pouvez configurer le téléphone Lync pour qu’il se déconnecte puis se reconnecte à intervalles réguliers (par exemple tous les trois mois).

4.  **Licences comptabilisées pour les téléphones PSTN prenant part à des conférences**
    
    Vous pouvez identifier manuellement le numéro de téléphone PSTN utilisé pour prendre part à la conférence et supprimer la licence générée par ce numéro de téléphone.

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a>Le panneau de configuration Lync Server cesse de fonctionner dans un environnement VMware après la mise à niveau vers Silverlight 5

**Exécuter**

Si vous utilisez le panneau de configuration Lync Server dans un environnement VMware, le panneau de configuration Lync Server peut cesser de fonctionner après la mise à niveau de Microsoft Silverlight vers la version 5.

**Palliatives**

Pour contourner ce problème, effectuez l’une des opérations suivantes :

  - Désinstallez Silverlight 5 et installez Silverlight 4 à [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156)partir de.

  - Accédez au panneau de configuration Lync Server à partir d’un ordinateur qui n’est pas un ordinateur virtuel VMware.
    
    Pour ce faire, vous pouvez démarrer le panneau de configuration Lync Server à partir du menu **Démarrer** de Windows sur le serveur, si les outils d’administration Lync Server sont installés sur l’ordinateur.
    
    Vous pouvez également accéder au panneau de configuration Lync Server à l’aide d’un navigateur Web. L’URL sera similaire au nom de\<domaine\_complet\_\>du pool https://frontal/CSCP.

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a>Les informations utilisateur du service de carnet d’adresses ne sont pas mises à jour après la modification du nom unique de l’utilisateur dans Active Directory.

**Exécuter**

Si le nom unique d’un utilisateur (également appelé DN) est modifié dans les services de domaine Active Directory (AD DS), toutes les modifications supplémentaires ne seront pas mises à jour dans le service de carnet d’adresses (ABS). Ceci n’affecte pas la connexion ou la présence de l’utilisateur, mais empêchera toute communication pour l’utilisateur si l’adresse SIP est également modifiée, car les recherches renverront une adresse IP obsolète.

**Palliatives**

Pour contourner ce problème, ne modifiez pas le nom unique de l’utilisateur. Si vous rétablissez la valeur précédente du nom unique de l’utilisateur, les mises à jour seront reflétées dans le service de carnet d’adresses.

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a>Installation

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a>L’utilisation de caractères non-ASCII peut entraîner l’échec du démarrage de Lync Server

**Exécuter**

Le programme d’installation échouera si le nom du dossier de destination inclut des caractères non-ASCII (UNICODE, jeu de caractères codés sur deux octets (DBCS), UTF-8 et UTF-16). De plus, le programme d’installation peut réussir, mais le serveur ne démarre pas si les caractères non ASCII sont contenus dans l’un des éléments suivants :

  - Nom de l'ordinateur

  - Nom du domaine

  - Nom d'utilisateur

  - URI SIP de l’utilisateur

  - Nom du compte de service

**Palliatives**

Utilisez uniquement des caractères ASCII dans le nom du dossier de destination, le nom de l’ordinateur, le nom de domaine, le nom d’utilisateur, l’URI SIP de l’utilisateur et les noms de compte de service.

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a>Le correctif logiciel pour « un endommagement de segment se produit lorsqu’un module appelle la méthode InsertEntityBody dans IIS 7,5 » doit être installé avant d’installer Lync Server 2013

**Exécuter**

Le correctif logiciel pour « un endommagement de segment se produit lorsqu’un module appelle la méthode[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)INSERTENTITYBODY dans IIS 7,5 » () décrit dans l'[https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)article 264886 de la base de connaissances Microsoft (), doit être installé avant l’installation de Lync Server 2013.

**Palliatives**

Téléchargez et installez le correctif à partir du centre de téléchargement [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)Microsoft à l’adresse.

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a>Lync Server 2013 ne parvient pas à installer sur le système d’exploitation Windows Server 2012 version RTM

**Exécuter**

L’installation de Lync Server 2013 échoue sur le serveur Windows Server 2012 ITA en raison de l’échec de l’installation de Windows fabric.

L’installation de Windows Fabric échoue car les traces de structure sont créées au format de l’heure HH:MM:SS, alors que dans Windows Server ITA le format de l’heure est HH.MM.SS.

**Palliatives**

Pour contourner ce problème, mettez à jour le registre système avant d’installer Lync Server 2013. La clé de Registre qui doit être mise à jour est\_la\\suivante : HKEY Users. Panneau\\de configuration\\par\\défaut international sTimeFormat. Modifiez la valeur de sTimeFormat sur HH : mm : SS à l’aide de l’interface de ligne de commande Windows PowerShell comme suit :

1.  Démarrez Windows PowerShell et exécutez les applets de commande suivantes :
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  Pour afficher la valeur actuelle, exécutez l’applet de commande suivante :
    
        Get-itemproperty $a -Name sTimeFormat
    
    Prenez note de la valeur actuelle de sTimeFormat afin de pouvoir la restaurer une fois l’installation terminée.

3.  Pour définir la nouvelle valeur, exécutez l’applet de commande suivante :
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  Une fois que Lync Server 2013 a été correctement installé, restaurez la valeur d’origine du sTimeFormat en exécutant l’applet de commande suivante :
    
        - Set-ItemProperty $a-name sTimeFormat "valeur de <notée à l’étape 3. au-dessus de>»

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a>Mobilité

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a>Problèmes liés aux clients mobiles pendant le processus de basculement de serveur

**Exécuter**

Lorsqu’un serveur Lync échoue et que le processus de basculement commence, les problèmes suivants peuvent affecter les utilisateurs des clients mobiles :

  - Aucun signal ou appel Lync entrant pendant 10 minutes maximum après le démarrage du basculement.

  - Impossible d’accepter les demandes de conversation entrantes

  - Impossible de joindre des réunions si le serveur défaillant est le serveur d’accueil de l’utilisateur

**Palliatives**

Il n’existe aucune solution de contournement à ce problème. Les fonctionnalités normales seront restaurées une fois le processus de basculement terminé.

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a>Si un utilisateur mobile refuse un appel entrant d’un autre point de terminaison Lync, l’appel est affiché en tant que conversion manquée sur les clients mobiles Lync.

**Exécuter**

Si un utilisateur mobile refuse un appel entrant et que l’appel provenait d’un autre point de terminaison Lync, l’appel est affiché en tant que conversation manquée dans le client mobile Lync et non dans la liste d’appels de périphérique.

**Palliatives**

Il n’existe aucune solution de contournement à ce problème.

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a>Le client mobile peut ne pas afficher le nom d’affichage d’un contact fédéré lors de la recherche de contacts

**Exécuter**

Le nom d’affichage des contacts fédérés peut ne pas être affiché dans certains scénarios, par exemple lors de la recherche d’un contact fédéré dans la liste des contacts. Cela peut se produire lorsqu’il n’existe aucun abonnement de présence actif pour le contact à partir du client mobile Lync.

**Palliatives**

Il n’existe aucune solution de contournement à ce problème.

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a>Dans le client mobile, les informations d’invité et d’horodatage sont manquantes dans une conversation manquée qui est une invitation à une conférence.

**Exécuter**

Dans le client mobile, lorsqu’une conversation manquée est une invitation à une conférence, les informations de l’invité et de l’horodatage sont manquantes dans le message de conversation manqué.

**Palliatives**

Il n’existe aucune solution de contournement à ce problème.

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a>Les utilisateurs de clients mobiles qui effectuent des appels à l’aide de VoIP ne sont pas en mesure de laisser des messages vocaux aux utilisateurs dont la messagerie vocale est configurée dans Exchange 2010 ou versions antérieures

**Exécuter**

Si un utilisateur de client mobile utilise la voix sur IP pour passer des appels, l’utilisateur ne pourra pas laisser de messages vocaux aux utilisateurs configurés pour utiliser la messagerie vocale dans Microsoft Exchange Server 2007 ou Microsoft Exchange Server 2010.

**Palliatives**

Pour contourner ce problème, utilisez Exchange 2010 avec SP1 ou une version ultérieure de Microsoft Exchange Server.

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a>Lors de l’utilisation de bloc avec une URL pour la configuration de la version du client sur les clients mobiles, un message d’erreur incorrect peut s’afficher.

**Exécuter**

Lors de l’utilisation de **bloc avec une URL** pour la configuration de la version du client sur les clients mobiles, un message d’erreur incorrect peut s’afficher lorsque la version du client n’est pas prise en charge.

**Palliatives**

Pour contourner ce problème, configurez la version du client de sorte qu’elle utilise **Block** au lieu de **bloquer avec l’URL**.

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a>Vidéoconférence

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a>Un logiciel antivirus exécuté sur des serveurs frontaux Lync Server 2013 peut entraîner le recyclage du domaine d’application, ce qui interrompt temporairement le service pour Lync Web App 2013, Lync Mobile 2010 et les clients Lync mobile 2013

**Exécuter**

Les logiciels antivirus peuvent déclencher des redémarrages de domaine d’application, ce qui peut entraîner des applications clientes d’API Web Lync Mobility service 2013 et Unified Communications (UC) (Lync Web App 2013, Lync Mobile 2010 et Lync mobile 2013) pour perdre leur état.

**Palliatives**

Pour contourner ce problème, excluez les dossiers suivants contenant des composants web et le .NET Framework de l’analyse antivirus. Pour plus d’informations, consultez l’article 312592 de la base de connaissances Microsoft « PRB : Random application restarts with’application Restarting » dans ASP.NET [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592)», à l’adresse.

Les dossiers suivants doivent être exclus :

  - % ProgramFiles%\\composants\\\\Web Microsoft Lync Server 2013 MCX\\ext

  - % ProgramFiles%\\composants\\\\Web Microsoft Lync Server 2013 MCX\\int

  - % ProgramFiles%\\composants\\\\Web Microsoft Lync Server 2013 Ucwa\\int

  - % ProgramFiles%\\composants\\\\Web Microsoft Lync Server 2013 Ucwa\\ext

  - % Windir%\\Microsoft.NET\\Framework64\\v 4.0.30319\\config

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a>Les contrôles ActiveX ou la prise en charge native de XMLHTTP doivent être activés dans Windows Internet Explorer pour rejoindre les conférences.

**Exécuter**

Si un utilisateur a désactivé la prise en charge XMLHTTP native et les contrôles ActiveX dans les paramètres du navigateur Internet Windows Internet Explorer, il ne pourra pas prendre part à une réunion si Internet Explorer est sélectionné comme navigateur par défaut.

**Palliatives**

Activez les contrôles ActiveX ou la prise en charge XMLHTTP native dans Internet Explorer.

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a>Le service de conférence Web Lync Server ne peut pas récupérer à partir du mode critique

**Exécuter**

Si le mode critique est activé pour l’archivage, en cas de défaillance du système, le mode critique démarre et les conférences ne fonctionnent plus pour les participants. Une fois que l’administrateur a éliminé cette défaillance (par exemple en résolvant un problème de base de données), le service de conférence de données ne récupère pas automatiquement et l’administrateur doit redémarrer manuellement le service de conférence pour que la conférence reprenne.

**Palliatives**

Un administrateur redémarrer manuellement le service de conférence une fois la défaillance système éliminée.

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a>Le service de conférence Web ignore le proxy HTTP pour les serveurs Office Web App externes

**Exécuter**

Si vous avez déployé un serveur Office Web Apps Server externe au service de conférence Web (autrement dit, un serveur qui n’est pas dans le réseau d’entreprise interne) sur Internet, le réseau de périmètre et le service de conférence Web nécessite un proxy HTTP pour se connecter à ceci, le La découverte d’Office Web Apps Server échouera. Le service de conférence Web ignore le paramètre proxy HTTP, tel que défini dans le générateur de topologies pour le programme d’installation d’Office Web Apps Server. Par conséquent, le client Lync ne pourra pas effectuer de partage Microsoft PowerPoint 2010 avec les autres participants à la Conférence. Si vous installez Lync Server localement et que vous configurez également Office Web Apps Server sur site sur le réseau interne, aucune configuration de proxy n’est requise.

**Palliatives**

La seule solution de contournement consiste à ne pas avoir de configuration de déploiement nécessitant l’utilisation d’un proxy HTTP pour communiquer avec un serveur Office Web Apps externe.

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a>L’ajout d’une vidéo à une conférence de fournisseurs de services d’audioconférence n’est pas pris en charge

**Exécuter**

L’ajout de vidéo n’est pas pris en charge si l’utilisateur participe à une conférence de fournisseur de services d’audioconférence pour l’audio.

**Palliatives**

Il n’existe aucune solution de contournement à ce problème.

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a>Les topologies avec IPv6 activé forcent la mise à jour automatique de Lync Web App Silverlight plug-in pour s’assurer que la fonctionnalité de partage d’écran peut fonctionner à partir de Lync Web App.

**Exécuter**

Lorsqu’une topologie est configurée avec IPv6 activé, les utilisateurs ne peuvent pas partager leur écran à partir du client Lync Web App si une version antérieure du plug-in de partage d’écran est déjà installée.

**Palliatives**

Pour forcer une mise à jour vers la version la plus récente du plug-in de partage d’écran lors de la participation à une réunion via Lync Web App, modifiez la valeur de **MinSupportedBuildVersion** de « 4.0.7457.0 » à « 4.0.7577.380 » dans les deux fichiers suivants :

  - Les composants\\\\\\Web de% ProgramFiles% Microsoft Lync Server\\15\\atteignent\\les plug-ins client\\ReachAppShPluginProperties. Xml

  - % ProgramFiles%\\les composants\\\\Web Microsoft Lync Server 15\\atteignent\\les plug-ins\\client ext\\ReachAppShPluginProperties. Xml

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a>Enterprise Voice

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a>Dans certains cas, un client Lync exécuté sur un ordinateur configuré pour utiliser la pile double IPv4 et IPv6 peut ne pas prendre en charge les fonctionnalités qui reposent sur le sous-réseau IP de l’ordinateur comme E911, la déviation du trafic multimédia, le contrôle d’admission des appels et le routage basé sur l’emplacement.

<div class="">


> [!NOTE]  
> Les informations contenues dans cette section concernent les mises à jour cumulatives pour Lync Server 2013 : février 2013.



</div>

**Exécuter**

Lorsqu’un client Lync est en cours d’exécution sur un ordinateur qui est activé pour la pile double IPv4 et IPv6 et sur la base de la résolution DNS du serveur proxy, le client peut utiliser l’adresse IPv6 de l’ordinateur pour se connecter. Une fois cette opération effectuée, le client Lync ne prend en charge que les fonctionnalités prises en charge par IPv6, ce qui exclut E911, la déviation du trafic multimédia, le contrôle d’admission des appels et le routage basé sur l’emplacement.

**Palliatives**

Pour contourner ce problème, désactivez la prise en charge D’ipv6 sur l’ordinateur client.

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a>Si voix entreprise n’est pas configurée pour un utilisateur, l’utilisateur devra utiliser le format E164 pour effectuer un appel sortant à partir d’une conférence.

**Exécuter**

Si voix entreprise n’est pas configurée pour un utilisateur, il devra utiliser le format E164 pour effectuer correctement un appel sortant d’une conférence. S’il n’utilise pas le format E164, l’utilisateur ne pourra pas effectuer d’appel sortant depuis la conférence.

**Palliatives**

Pour contourner ce problème, les utilisateurs qui ne sont pas activés pour voix entreprise doivent effectuer des appels sortants à partir d’une conférence à l’aide de numéros au format E164.

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a>Présence

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a>Si un utilisateur a sélectionné l’option « bloquer toutes les invitations et communications » alors que le magasin de contacts unifié est activé pour l’utilisateur, le statut de présence n’est pas rejeté quand il devrait l’être.

**Exécuter**

Si un utilisateur a sélectionné l’option « Bloquer toutes les invitations et communications » alors que le magasin de contacts unifié est activé pour cet utilisateur, le statut de présence n’est pas rejeté quand il devrait l’être.

**Palliatives**

Pour contourner ce problème, vous pouvez désactiver le magasin de contacts unifié pour l’utilisateur. Pour cela, exécutez les applets de commande suivantes :

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

Par exemple :

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a>Office Communications Server 2007 R2 les utilisateurs hébergés sur site ne peuvent pas voir le statut de présence des utilisateurs Skype entreprise Online dans des déploiements hybrides-hybrides

**Exécuter**

Le problème peut se produire dans un déploiement hybride lorsque vous utilisez un directeur Lync Server 2013.

Le statut de présence des utilisateurs hébergés sur Skype entreprise Online est affiché en tant que présence inconnue pour les utilisateurs locaux. En outre, les utilisateurs hébergés sur Skype entreprise Online ne peuvent pas voir le statut de présence des utilisateurs locaux d’Office Communications Server R2.

**Palliatives**

Pour contourner partiellement ce problème, modifiez le serveur d’accueil (msRTCSIP-presencehomeserver) des utilisateurs de Skype entreprise Online afin qu’ils pointent vers un pool Lync Server 2013 local au lieu du directeur de Lync Server 2013. Vous pouvez modifier ce paramètre sur le serveur frontal local.

Cette solution de contournement affiche correctement l’état de présence des utilisateurs hébergés sur Office Communications Server 2007 R2 aux utilisateurs de Skype entreprise online.

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a>Application Response Group, application de parcage d’appel et prise d’appel de groupe

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a>Un appelant peut entendre une seconde de musique en attente lors de l’établissement d’un appel avec la partie de récupération

<div class="">


> [!NOTE]  
> Les informations contenues dans cette section concernent les mises à jour cumulatives pour Lync Server 2013 : février 2013.



</div>

**Exécuter**

Lorsqu’un appel est récupéré via la prise d’appel de groupe, l’appelant peut entendre une seconde de l’attente musicale lors de l’établissement de l’appel auprès du destinataire.

**Palliatives**

Il n’existe aucune solution de contournement à ce problème.

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a>Un agent Response Group peut se connecter et se déconnecter par le biais d’une console de l’agent Lync Server 2010 pour les groupes d’agents formels Lync Server 2010 uniquement

**Exécuter**

Un agent Response Group Lync Server 2013 peut se connecter et se déconnecter par le biais d’une console de l’agent Lync Server 2010 pour les groupes d’agents formels Lync Server 2010 uniquement. Dans la console de l’agent Lync Server 2010, les utilisateurs peuvent uniquement voir le groupe de réponse Lync Server 2010 auquel ils appartiennent. Ils ne peuvent pas voir les groupes de réponses Lync Server 2013 auxquels ils appartiennent.

**Palliatives**

Si l’agent Response Group est un utilisateur Lync Server 2013 et qu’il fait partie d’un groupe d’agents formels Lync Server 2013, l’utilisateur doit accéder à la console de l’agent Lync Server 2013 directement via un lien Web dans un navigateur pour se connecter et se déconnecter des groupes d’agents Lync Server 2013.

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a>Un agent Response Group Lync Server 2010 ne peut pas passer d’appels pour le compte d’un groupe de réponse Lync Server 2013

**Exécuter**

Un utilisateur Lync Server 2010 qui est un agent d’un groupe Response Group Lync Server 2013 ne peut pas effectuer d’appel pour le compte du groupe Response Group. Le groupe de réponse Lync Server 2013 ne sera pas disponible dans le client Lync pour passer un appel.

**Palliatives**

Pour contourner ce problème, vous devez déplacer l’utilisateur Lync Server 2010 vers Lync Server 2013.

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a>La suppression d’un groupe Response Group de Lync Server 2010 après sa migration vers Lync Server 2013 empêchera le groupe Response Group d’accepter les appels entrants.

**Exécuter**

Si un groupe Response Group qui a été migré de Lync Server 2010 vers Lync Server 2013 est supprimé de Lync Server 2010 via le panneau de configuration Lync Server ou Lync Server Management Shell, le groupe Response Group dans Lync Server 2013 cessera de recevoir les appels entrants.

**Palliatives**

Pour contourner ce problème, ne supprimez pas de groupes Response Group de Lync Server 2010 qui ont été migrés de Lync Server 2010 vers Lync Server 2013.

Si le groupe Response Group a déjà été supprimé, vous devez le redéployer dans Lync Server 2013.

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a>Lorsqu’un nouveau flux de travail géré est défini sur inactif lors de sa création, le déploiement du flux de travail échoue

**Exécuter**

Lorsqu’un nouveau flux de travail géré est défini comme inactif lors de sa création, son déploiement échoue. Ce problème se produit quand le flux de travail est défini comme inactif au moment de sa création, mais il n’affecte pas un flux de travail modifié et défini comme inactif après son déploiement.

**Palliatives**

Lors de la création et du déploiement d’un flux de travail, définissez le flux de travail comme actif, puis déployez-le. Une fois le déploiement réussi, vous pouvez modifier le flux de travail et le définir comme inactif.

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a>La suppression d’un groupe Response Group du pool propriétaire empêche le groupe Response Group du pool de sauvegarde d’accepter les appels entrants pendant le basculement si le groupe Response Group a été importé dans le pool de sauvegarde

**Exécuter**

Si un groupe Response Group appartenant au pool principal a été importé dans le pool de sauvegarde sans remplacer le propriétaire et que le groupe Response Group est supprimé du pool propriétaire, le groupe Response Group dans le pool de sauvegarde n’accepte aucun appel entrant lors du basculement.

**Palliatives**

Vous devrez redéployer le groupe Response Group dans le pool principal. Vous devrez ensuite exporter la configuration Response Group à partir du pool principal et l’importer à nouveau dans le pool de sauvegarde.

Vous pouvez également recréer le groupe Response Group dans le pool de sauvegarde. Dans ce cas, le pool de sauvegarde sera le pool propriétaire du groupe Response Group.

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a>Un appel parqué ne peut pas être récupéré à partir de l’application de parcage d’appel si la demande de récupération est exécutée pour le compte d’un groupe Response Group

**Exécuter**

Lorsque les conditions suivantes sont remplies, une demande de récupération pour un appel parqué échoue :

  - Un agent fait partie d’un groupe Response Group anonyme

  - L’agent tente de récupérer un appel parqué à partir de l’application de parcage d’appel via le groupe Response Group anonyme

  - L’agent tente de récupérer l’appel en composant le numéro d’orbite par le biais de l’option Appeler de la part de ou par le biais de la même option dans le client intendant Lync.

**Palliatives**

Il n’existe aucune solution de contournement à ce problème. L’appel parqué doit être récupéré sans faire pour le compte d’un groupe Response Group.

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a>Panneau de configuration Lync Server, générateur de topologies et outil de planification

<div>

## <a name="planning-tool-limitations"></a>Limitations de l’outil de planification

<div class="">


> [!NOTE]  
> Les informations contenues dans cette section concernent les mises à jour cumulatives pour Lync Server 2013 : février 2013.



</div>

**Exécuter**

Lors de la planification de votre déploiement, l’outil de planification présente les limitations suivantes :

  - Il y a un maximum de 10 sites centraux pris en charge

  - Chaque site central peut comporter 14 sites de succursale au maximum.

  - Chaque site central peut comporter jusqu’à 240 000 utilisateurs

En outre, l’outil de planification n’inclut pas de valeurs pour les éléments suivants lors du calcul de la topologie recommandée :

  - Le nombre d’utilisateurs hébergés en ligne ;

  - Pourcentage d’utilisateurs activés pour la Fédération XMPP

  - Pourcentage d’utilisateurs qui utilisent Lync Web App

**Palliatives**

Il n’existe aucune solution de contournement à ces problèmes. Pour plus d’informations sur l’outil de planification, voir [conception de la topologie pour Lync Server 2013 à l’aide de l’outil de planification](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a>L’outil de planification ne peut pas utiliser des adresses IP précédemment définies pour le réseau de périmètre lors de la mise à jour des options

**Exécuter**

Une fois que vous avez terminé votre conception à l’aide de l’outil de planification, si vous modifiez les options réseau Edge, des adresses IP supplémentaires peuvent être ajoutées à la conception au lieu de mettre à jour les adresses IP existantes. Cela peut se produire lorsque vous affichez les détails du diagramme de réseau Edge, que vous sélectionnez **Cliquer ici pour mettre à jour vos options**, puis que vous sélectionnez réseau Edge dans la boîte de dialogue Options de configuration, et que vous sélectionnez réseau Edge **, sélectionnez je souhaite utiliser les mêmes noms de domaine complets et adresses IP, mais des ports différents pour les services Edge sur mon serveur Edge**. L’application des modifications peut entraîner l’ajout de nouvelles adresses IP et de nouveaux serveurs Edge à la conception.

**Palliatives**

Il n’existe actuellement aucune solution de contournement à ce problème.

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a>Dans le panneau de configuration Lync Server, « déplacer tous les utilisateurs vers le pool » peut ne pas fonctionner comme prévu

**Exécuter**

Lors de l’utilisation du panneau de configuration Lync Server pour déplacer tous les utilisateurs d’un pool vers un autre dans un environnement Active Directory complexe, tel qu’un autre avec des contrôleurs de domaine et des domaines parents/enfants, un message d’erreur peut être renvoyé indiquant que « l’utilisateur spécifié n’est pas un utilisateur hérité, utilisez plutôt l’applet de commande Move-CsUser. ». Ceci est le résultat d’un temps de réplication plus long dans les environnements Active Directory complexes.

**Palliatives**

Pour contourner ce problème, effectuez l’une des opérations suivantes :

  - Utilisez des filtres dans le panneau de configuration Lync Server pour rechercher des utilisateurs hérités, sélectionnez ces utilisateurs, puis utilisez la **commande déplacer les utilisateurs sélectionnés vers le pool** au lieu de **déplacer tous les utilisateurs vers le pool**.

  - Utilisez Lync Server Management Shell pour déplacer des utilisateurs hérités par lots à l’aide des applets de commande Lync Server.

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a>Le panneau de configuration Lync Server cesse de fonctionner dans un environnement VMware après la mise à jour du plug-in de navigateur Microsoft Silverlight vers la version 5

**Exécuter**

Si vous utilisez le panneau de configuration Lync Server dans un environnement VMware, le panneau de configuration Lync Server peut cesser de fonctionner après la mise à niveau de Silverlight vers la version 5.

**Palliatives**

Pour contourner ce problème, effectuez l’une des opérations suivantes :

  - Désinstallez Silverlight 5, puis installez Silverlight 4 à [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0)partir de.

  - Ouvrez le panneau de configuration Lync Server à partir d’un ordinateur qui n’est pas un ordinateur virtuel VMware.
    
    Pour ouvrir le panneau de configuration Lync Server à partir d’un ordinateur distant, installez les outils d’administration Lync Server sur l’ordinateur, puis démarrez le panneau de configuration Lync Server à partir du menu **Démarrer** de Windows.
    
    Vous pouvez également ouvrir le panneau de configuration Lync Server en entrant l’URL dans un navigateur Web. L’URL sera similaire au nom de\<domaine\_complet\_\>du pool https://frontal/CSCP.

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a>Un administrateur ne peut pas exécuter la cmdlet Uninstall-csMirrorDB après la suppression de la base de données de mise en miroir dans le générateur de topologies

**Exécuter**

Lorsqu’un administrateur désactive une base de données de mise en miroir dans le générateur de topologie, puis supprime la base de données de mise en miroir dans le générateur de topologie, un message s’affiche dans la liste à faire pour que l’administrateur puisse exécuter la cmdlet **Uninstall-csMirrorDatabase** afin de supprimer la mise en miroir de SQL Server. Quand l’administrateur tente d’exécuter l’applet de commande, l’opération échoue.

**Palliatives**

Pour supprimer la mise en miroir SQL d’un pool dans le générateur de topologies, vous devez d’abord utiliser une cmdlet pour supprimer le miroir dans SQL Server. Vous pouvez ensuite utiliser le Générateur de topologie pour supprimer le miroir de la topologie. Pour supprimer le miroir dans SQL Server, utilisez l’applet de commande suivante :

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

Par exemple, pour supprimer la mise en miroir et les bases de données pour les bases de données utilisateur, tapez ce qui suit :

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

Le paramètre *DropExistingDatabasesOnMirror* permet de supprimer les bases de données affectées du miroir. Ensuite, pour supprimer le miroir de la topologie, procédez comme suit :

1.  Dans le Générateur de topologie, cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.

2.  Désactivez l’option **Activer la mise en miroir du magasin SQL** et cliquez sur **OK**.

3.  Publiez la topologie.

<div class="">


> [!IMPORTANT]  
> Chaque fois que vous modifiez une relation de mise en miroir de base de données principale, vous devez redémarrer tous les serveurs frontaux du pool.



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a>Les erreurs de validation sont renvoyées dans le générateur de topologie lorsqu’un administrateur tente de supprimer un déploiement avec un pool frontal disposant d’un magasin de témoins associé

**Exécuter**

Si un administrateur tente d’utiliser la commande **supprimer le déploiement** dans le générateur de topologie pour supprimer un déploiement qui inclut un pool frontal avec un magasin de témoins associé, une erreur de validation s’affiche dans le générateur de topologies et l’action ne se poursuit pas.

**Palliatives**

Pour contourner ce problème, effectuez l’une des opérations suivantes :

  - Supprimez le magasin de témoins avant d’essayer de supprimer le déploiement.

  - Ajoutez un magasin de témoins pour le pool frontal, puis supprimez-le.

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a>Les informations de déploiement du serveur de conversation permanente ne sont pas cohérentes entre l’outil de planification et le générateur de topologies

**Exécuter**

Lorsque l’outil de planification Lync Server 2013, affiche le diagramme de topologie de site pour un déploiement de serveur de conversation permanente avec la récupération d’urgence activée, le diagramme de topologie de site inclut plusieurs sites (physiques), avec des serveurs de conversation permanente affectés de manière équitable. site. Dans le générateur de topologie, tous les serveurs de conversation permanente sont représentés comme appartenant à un site unique (logique) et sont répertoriés sous le même nœud de pool de serveurs de conversation permanente.

**Palliatives**

Il n’existe actuellement aucune solution de contournement à ce problème. L’utilisateur doit analyser la sortie de l’outil de planification pour le déploiement du serveur de conversation permanente et modifier le plan pour répondre à ses besoins spécifiques.

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a>Localisation

<div>

## <a name="monitoring"></a>Surveillance

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a>L’Assistant déployer les rapports de surveillance affiche des caractères incorrects dans certaines circonstances lors de l’utilisation de la version d’Asie orientale de Lync Server

**Exécuter**

Lors de l’utilisation d’une version d’Asie orientale de Lync Server 2013 (par exemple, chinois (simplifié), chinois (traditionnel), japonais ou coréen) sur un système d’exploitation dont les paramètres régionaux système ne sont pas définis sur une langue d’Asie de l’est, l’Assistant déployer les rapports de surveillance afficher des points d’interrogation ou d’autres caractères au lieu de messages localisés.

**Palliatives**

Pour corriger ce problème, définissez les paramètres régionaux du système d’exploitation et de Lync Server 2013 dans la même langue, ce qui affichera correctement tous les messages.

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a>Panneau de commande Lync Server

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a>Dans certains cas, le premier élément dans la barre de navigation supérieure sur une page du panneau de configuration Lync Server disparaît lorsque l’utilisateur clique sur le dernier élément de la barre de navigation supérieure.

**Exécuter**

Il existe trois cas connus dans lesquels le fait de cliquer sur le dernier élément dans la barre de navigation supérieure sur une page du panneau de configuration Lync Server entraîne la disparition du premier élément dans la barre de navigation supérieure :

  - Dans la version française, dans la page « Fédération et accès externe », l’élément « Stratégie d’accès externe » disparaît lorsque vous cliquez sur « Partenaires fédérés XMPP ».

  - Dans la version allemande, dans la page « Clients », l’élément « Clientversionskonfiguration » disparaît lorsque vous cliquez sur « Pushbenachrichtigungskonfiguration ».

  - Dans la version russe, dans la page « Конфигурация сети », l’élément « Глобально » disparaît lorsque vous cliquez sur « Маршрут региона ».

**Palliatives**

Pour contourner ce problème, actualisez la page du panneau de configuration Lync Server dans votre navigateur. La page sera chargée dans le navigateur avec tous les éléments de la barre de navigation supérieure affichés.

</div>

</div>

<div>

## <a name="address-book"></a>Carnet d’adresses

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a>L’indexation dans le carnet d’adresses ne fonctionne pas comme prévu dans certaines langues

<div class="">


> [!NOTE]  
> Les informations contenues dans cette section concernent les mises à jour cumulatives pour Lync Server 2013 : février 2013.



</div>

Si les propriétés d’un utilisateur contiennent un champ indexé et que ce champ contient uniquement des caractères qui ne peuvent pas être indexés, l’utilisateur n’apparaît pas dans les recherches effectuées dans le carnet d’adresses.

Les paramètres régionaux et les caractères suivants ne peuvent pas être indexés :

  - Caractères latins, grecs et arméniens en majuscules

  - Caractères accentués avec des majuscules

  - Thaï

  - Lao

  - Birman

  - Dévanâgarî

  - Éthiopien

  - Tibétain

  - Bengali

  - Goudjrati

  - Télougou

  - Tous les autres scripts indo-aryens

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a>Lync Web App, Web Scheduler et Web Components

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a>La langue de secours pour certaines langues dans Lync Web Scheduler, Dial-in, Join Launcher, la gestion des salles de conversation permanente et OCTab peut ne pas fonctionner comme prévu

**Exécuter**

Lors de la sélection d’un paramètre régional neutre dans un navigateur Web (dans Internet Explorer, par exemple, le nom de la langue sans spécification \[supplémentaire\], comme « non norvégien ») au lieu d’un paramètre régional spécifiant la langue, le script et les paramètres régionaux \[(par exemple\], « norvégien, Bokmål (Norvège) NB-no ») peut entraîner un comportement d’affichage inattendu pour certaines langues dans Lync Web Scheduler, Dial-in, le lanceur de conversation permanente et OCTab Par exemple, les utilisateurs peuvent voir la page en anglais lorsque l’une des langues suivantes est sélectionnée :

  - Norvégien

  - Portugais

  - Serbe

**Palliatives**

Si vous souhaitez sélectionner une langue avec un paramètre régional neutre, assurez-vous de toujours ajouter également la langue avec un paramètre régional spécifique (avec script et/ou code de pays) comme langue supplémentaire dans la liste des préférences linguistiques de votre navigateur.

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a>La prise en charge des paramètres régionaux azéri et ouzbek avec Lync Web Scheduler, Dial-in, Join Launcher, la gestion des salles de conversation permanente et OCTab dans certains navigateurs Web est limitée.

<div class="">


> [!NOTE]  
> Les informations contenues dans cette section concernent les mises à jour cumulatives pour Lync Server 2013 : février 2013.



</div>

**Exécuter**

Lorsque vous utilisez Internet Explorer 8 ou Internet Explorer 9 et que vous définissez la langue du navigateur sur azéri (latin) ou ouzbek (latin), les pages du lanceur d’appels entrants et de jonction s’afficheront en anglais ou dans la langue par défaut définie dans le navigateur.

Lorsque vous utilisez des navigateurs Firefox ou chrome, et que vous définissez la langue du navigateur sur azéri (latin) ou ouzbek (latin), l’application Lync Web App, Lync Web Scheduler et RGS OCTab seront affichées en anglais ou dans la langue par défaut définie pour le navigateur.

Les paramètres régionaux ouzbek (latin) ne sont pas pris en charge dans le navigateur Safari.

**Palliatives**

Il n’existe pas de solution de contournement pour ces problèmes.

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a>La flèche déroulante est manquante pour la liste « joindre une réunion de » dans la version roumaine de Lync Web App

**Exécuter**

Lorsqu’un utilisateur qui utilise la version roumaine de Lync Web App effectue les étapes suivantes, la flèche déroulante n’est pas affichée pour **rejoindre une réunion** dans la liste déroulante :

1.  Sélectionnez **Mémoriser mon adresse sur cet ordinateur** sous l’onglet **Général**.

2.  Sélectionnez l’onglet **Téléphone**.

3.  Cliquez sur la liste déroulante pour **Rejoindre la réunion**.
    
    Les utilisateurs ne verront pas une flèche indiquant qu’il existe davantage d’options que l' **application Web Lync**par défaut, notamment : **ne pas participer** à l’audio (en roumain, « nu se asociaža la composantea audio ») et le **nouveau numéro**« (en roumain, «număr Nou »).

**Palliatives**

Bien que la flèche de cette liste déroulante ne soit pas affichée, les utilisateurs peuvent tout de même sélectionner les paramètres supplémentaires dans la liste en cliquant sur la valeur par défaut.

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a>Lors de l’utilisation de la version turque de Lync Web Scheduler, une réunion ne peut pas être enregistrée lors de l’utilisation de l’option « personnes que je choisis » sous « qui est un présentateur ».

**Exécuter**

Lors de la création ou de la modification d’une réunion dans la version turque de Lync Web Scheduler, l’option « Personnes que j’ai choisies » sous « Présentateur » n’est pas prise en charge. Lorsque cette option est sélectionnée, la réunion ne peut pas être enregistrée. Au lieu de cela, un message d’erreur s’affiche et indique qu’une ou plusieurs personnes ne peuvent pas être présentateurs.

**Palliatives**

Pour contourner ce problème, les utilisateurs peuvent sélectionner l’option par défaut « Personnes de ma société » ou tout autre choix tel que « Seul l’organisateur » ou « Tout le monde, y compris les personnes extérieures à ma société ». L’organisateur peut rétrograder ou promouvoir les personnes à leur rôle correct ultérieurement, une fois qu’elles ont rejoint la réunion.

En guise d’alternative, les utilisateurs qui comprennent une autre langue peuvent modifier la sélection de langue dans leur navigateur, choisir l’une des 43 langues prises en charge et essayer d’utiliser l’option « Personnes que j’ai choisies ».

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a>Copyright

Ce document traite d’une version préliminaire d’un produit logiciel qui pourra faire l’objet de modifications substantielles préalablement à la version commerciale finale et constitue des informations confidentielles et appartenant à Microsoft Corporation. Il est divulgué conformément à un accord de confidentialité entre le bénéficiaire et Microsoft. Ce document est fourni uniquement à titre informatif et Microsoft exclut toute garantie, expresse ou implicite, en ce qui concerne ce document. Les informations contenues dans ce document, y compris les URL et autres références à des sites web Internet, pourront faire l’objet de modifications sans préavis. L’utilisateur reconnaît assumer tous les risques liés à l’utilisation de ce document. Sauf mention contraire, les noms de sociétés, d’organisations, de produits, de personnes ou les événements mentionnés dans les exemples sont fictifs. Toute ressemblance avec des noms ou des événements réels est purement fortuite et involontaire. L’utilisateur est tenu d’observer la réglementation relative aux droits d’auteur applicable dans son pays. Aucune partie de ce document ne peut être reproduite, stockée ou introduite dans un système de restitution, ou transmise à quelque fin ou par quelque moyen que ce soit (électronique, mécanique, photocopie, enregistrement ou autre) sans la permission expresse et écrite de Microsoft Corporation.

Microsoft peut détenir des brevets, avoir déposé des demandes d’enregistrement de brevets ou être titulaire de marques, droits d’auteur ou autres droits de propriété intellectuelle portant sur tout ou partie des éléments qui font l’objet du présent document. Sauf stipulation expresse contraire d’un contrat de licence écrit de Microsoft, la fourniture de ce document n’a pas pour effet de vous concéder une licence sur ces brevets, marques, droits d’auteur ou autres droits de propriété intellectuelle.

© 2012 Microsoft Corporation. Tous droits réservés.

Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook et SQL Server sont soit des marques de Microsoft Corporation, soit des marques déposées de Microsoft Corporation, aux États-Unis et/ou dans d’autres pays/régions.

Toutes les autres marques sont la propriété de leur détenteur respectif.

</div>

</div>

<span> </span>

</div>

</div>

</div>

