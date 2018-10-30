---
title: 'Skype Entreprise Server 2015 : test de récupération d’urgence'
TOCTitle: Test de récupération d’urgence
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn747887(v=OCS.15)
ms:contentKeyID: 62293518
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test de récupération d’urgence dans Skype Entreprise Server 2015

 

_**Dernière rubrique modifiée :** 2015-01-26_

Effectuez une récupération du système pour un serveur de pools Lync Server 2013 afin de tester la procédure de récupération d’urgence documentée. Ce test simule une défaillance matérielle complète d’un serveur et permet de s’assurer que les ressources, les plans et les données sont disponibles pour la récupération. Essayez d’alterner l’angle du test chaque mois afin que votre organisation teste chaque fois la défaillance d’un autre serveur ou d’un autre équipement.

Notez que le calendrier des tests de récupération d'urgence de votre organisation varie. Il est très important que les tests de récupération d’urgence ne soient ni ignorés ni négligés.


Exportez votre topologie, vos stratégies et vos paramètres de configuration de Lync Server 2013 dans un fichier. Ce fichier peut, entre autres, être utilisé pour restaurer ces informations dans le magasin central de gestion après une mise à niveau, une défaillance matérielle ou un autre problème ayant entraîné une perte de données.

Importez votre topologie, vos stratégies et vos paramètres de configuration de Lync Server 2013 dans le magasin central de gestion ou sur l’ordinateur local, comme indiqué dans les commandes suivantes :

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

Pour sauvegarder les données Lync Server 2013 de production :

  - Sauvegardez les bases de données RTC et LCSLog en utilisant la procédure de sauvegarde SQL Server standard afin de vider la base de données dans un fichier ou sur un périphérique de vidage sur bande.

  - Sauvegardez les données dans un fichier ou sur une bande à l’aide de l’application de sauvegarde tierce.

  - Créez un export XML de la base de données RTC intégrale à l’aide de l’applet de commande Export-CsUserData.

  - Sauvegardez le contenu d’une réunion et les journaux de conformité à l’aide de la sauvegarde du système de fichiers ou d’un utilitaire de sauvegarde/restauration tiers.

  - Sauvegardez les paramètres de sauvegarde de Lync Server 2013 à l’aide de l’outil de ligne de commande.

La première étape de la procédure de basculement comporte un déplacement forcé des utilisateurs du pool de production vers le pool de récupération d’urgence.

Il s’agit d’un déplacement forcé, car le pool de production n’est pas disponible pour accepter le déplacement des utilisateurs.

La procédure de déplacement des utilisateurs dans Lync Server 2013 consiste effectivement en une modification d’un attribut de l’objet compte d’utilisateur, ainsi qu’en une mise à jour des enregistrements dans la base de données SQL RTC.

Ces données peuvent être restaurées par le biais des deux procédures suivantes :

  - La base de données RTC peut être restaurée à partir du périphérique de vidage de sauvegarde initial de l’SQL Server de production à l’aide de la procédure de restauration standard de SQL Server ou d’un utilitaire de sauvegarde/restauration tiers.

  - Les données de contact des utilisateurs peuvent être restaurées avec l’utilitaire DBIMPEXP.exe à l’aide du fichier XML créé à partir de l’export SQL Server de production.

Une fois ces données restaurées, les utilisateurs peuvent se connecter effectivement au pool de récupération d’urgence de Lync Server 2013 et l’utiliser de façon habituelle.

Pour que les utilisateurs puissent se connecter au pool de récupération d'urgence de Lync Server 2013, l’enregistrement DNS doit être modifié.

Le pool Lync Server 2013 de production est référencé par les clients à l’aide de la configuration automatique et des enregistrements SRV du serveur de noms de domaine (DNS) :

  - SRV : \_sip.\_tls.\<domaine\> /CNAME: SIP.\<domaine\>

  - CNAME : SIP.\<domaine\> /cvc-pool-1.\<domaine\>

Pour faciliter le basculement, cet enregistrement CNAME doit être mis à jour de manière à référencer le nom de domaine complet (FQDN) DROCSPool :

  - CNAME : SIP.\<domaine\> /DROCSPool.\<domaine\>

  - Sip.\<domaine\>

  - AV.\<domaine\>

  - webconf.\<domaine\>

  - OCSServices.\<domaine\>

> [!IMPORTANT]  
> Pour plus d’informations sur les procédures d’administration et de gestion, reportez-vous à la rubrique <a href="lync-server-2013-backing-up-and-restoring-lync-server.md">Sauvegarde et restauration de Lync Server 2013</a>.

## Voir aussi

#### Concepts

[Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[Applets de commande pour la sauvegarde et la haute disponibilité](https://docs.microsoft.com/en-us/powershell/module/skype/?view=skype-ps)  

#### Autres ressources

[Import-CsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Import-CsConfiguration)  
[Sauvegarde et restauration de Lync Server 2013](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[Gestion de la récupération d’urgence, de la haute disponibilité et du service de sauvegarde de Lync Server 2013](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)

