---
title: "LS 2013 : Dés. hérit. aut. sur cont. des obj. Ordi., Util. ou InetOrgPerson"
TOCTitle: Désactivation de l’héritage des autorisations sur les conteneurs des objets Ordinateur, Utilisateur ou InetOrgPerson
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412970(v=OCS.15)
ms:contentKeyID: 49298761
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Désactivation de l’héritage des autorisations sur les conteneurs des objets Ordinateur, Utilisateur ou InetOrgPerson dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-12-19_

Dans les services de domaine Active Directory, les objets Utilisateur et Ordinateur sont souvent placés dans des unités d’organisation spécifiques dans lesquelles l’héritage des autorisations a été désactivé afin de sécuriser la délégation d’administration et de permettre l’utilisation d’objets de stratégie de groupe pour l’application de stratégies de sécurité.

La préparation de domaine et l’activation de serveur définissent les entrées de contrôle d’accès nécessaires à Lync Server 2013. Quand l’héritage des autorisations est désactivé, les groupes de sécurité Lync Server ne peuvent pas hériter ces entrées de contrôle d’accès. Quand ces autorisations ne sont pas héritées, les groupes de sécurité Lync Server ne peuvent pas accéder aux paramètres et deux problèmes se posent :

  - Pour administrer les objets Utilisateur, InetOrgPerson et Contact et faire fonctionner les serveurs, les groupes de sécurité Lync Server nécessitent des entrées de contrôle d’accès définies par la procédure de préparation de domaine sur les jeux de propriétés de chaque utilisateur, les communications en temps réel (service RTC), la recherche d’utilisateur RTC et les informations publiques. Quand l’héritage des autorisations est désactivé, les groupes de sécurité n’héritent pas ces entrées de contrôle d’accès et ne peuvent pas gérer les serveurs ou les utilisateurs.

  - Pour détecter les serveurs et les pools, les serveurs exécutant Lync Server s’appuient sur les entrées de contrôle d’accès définies par l’activation sur des objets liés à l’ordinateur, notamment les objets Conteneur et Serveur Microsoft. Quand l’héritage des autorisations est désactivé, les groupes de sécurité, les serveurs et les pools n’héritent pas de ces entrées de contrôle d’accès et ne peuvent pas les exploiter.

Pour résoudre ces problèmes, Lync Server propose l’applet de commande **Grant-CsOuPermission**. Elle définit les entrées de contrôle d’accès Lync Server directement nécessaires à un conteneur et aux unités d’organisation spécifiées, mais aussi aux objets dans le conteneur ou l’unité d’organisation.

## Définir des autorisations sur les objets Utilisateur, InetOrgPerson et Contact après exécution de la préparation du domaine

Dans un environnement Active Directory verrouillé dans lequel l’héritage des autorisations est désactivé, la préparation du domaine ne définit pas les entrées de contrôle d’accès nécessaires sur les conteneurs ou les unités d’organisation abritant des objets Utilisateur ou InetOrgPerson à l’intérieur du domaine. Dans ce cas, vous devez exécuter l’applet de commande **Grant-CsOuPermission** sur chaque conteneur ou unité d’organisation contenant les objets Utilisateur ou InetOrgPerson pour lesquels l’héritage des autorisations est désactivé. Si vous avez déployé une topologie de forêt centrale, vous devez également exécuter cette procédure sur les conteneurs ou les unités d’organisation qui détiennent des objets Contact. Pour plus d’informations sur les topologies de forêt centrale, reportez-vous à [Topologies Active Directory prises en charge dans Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) dans la documentation de prise en charge. Le paramètre ObjectType précise le type d’objet. Le paramètre OU spécifie l’unité d’organisation.

Cette applet de commande ajoute directement les entrées de contrôle d’accès requises sur les conteneurs ou les unités d’organisation spécifiées et les objets Utilisateur et InetOrgPerson qu’ils contiennent.

Pour exécuter cette applet de commande, vous devez bénéficier de droits d’utilisateur identiques à ceux utilisés en tant que membre du groupe Administrateurs de domaine. Si les entrées de contrôle d’accès des utilisateurs authentifiés ont également été supprimées dans l’environnement verrouillé, vous devez octroyer des entrées de contrôle d’accès en lecture à ce compte sur les conteneurs ou les unités d’organisation concernées dans le domaine racine de la forêt, comme décrit dans [Suppression des autorisations d’utilisateur authentifié dans Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) ou bien utiliser un compte qui est membre du groupe Administrateurs d’entreprise.

**Pour définir les entrées de contrôle d’accès requises pour les objets Utilisateur, InetOrgPerson et Contact**

1.  Ouvrez une session sur un ordinateur lié au domaine en utilisant un compte qui est membre du groupe Administrateurs de domaine ou doté de droits d’utilisateur équivalents.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez :
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.
    
    Exemple :
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  Dans le fichier journal, recherchez le résultat d’exécution **\<Opération réussie\>** à la fin de chaque tâche, vérifiez que les autorisations ont été définies, puis fermez la fenêtre du journal. Vous pouvez également exécuter la commande suivante pour déterminer si les autorisations ont été définies :
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    Exemple :
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

## Définir des autorisations sur les objets Ordinateur après exécution de la préparation du domaine

Dans un environnement Active Directory verrouillé dans lequel l’héritage des autorisations est désactivé, la préparation du domaine ne définit pas les entrées de contrôle d’accès nécessaires sur les conteneurs ou les unités d’organisation abritant des objets Ordinateur à l’intérieur du domaine. Dans ce cas, vous devez exécuter l’applet de commande **Grant-CsOuPermission** sur chaque conteneur ou unité d’organisation disposant d’ordinateurs dotés de Lync Server et pour lesquels l’héritage des autorisations est désactivé. Le paramètre ObjectType précise le type d’objet.

Cette procédure ajoute directement les entrées de contrôle d’accès requises sur les conteneurs spécifiés.

Pour exécuter cette applet de commande, vous devez bénéficier de droits d’utilisateur identiques à ceux utilisés en tant que membre du groupe Administrateurs de domaine. Si les entrées de contrôle d’accès des utilisateurs authentifiés ont également été supprimées, vous devez octroyer des entrées de contrôle d’accès en lecture à ce compte sur les conteneurs concernés dans le domaine racine de la forêt, comme décrit dans [Suppression des autorisations d’utilisateur authentifié dans Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) ou bien utiliser un compte qui est membre du groupe Administrateurs d’entreprise.

**Pour configurer les entrées de contrôle d’accès requises pour les objets Ordinateur**

1.  Ouvrez une session sur l’ordinateur du domaine en utilisant un compte qui est membre du groupe Administrateurs de domaine ou doté de droits d’utilisateur équivalents.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez :
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.
    
    Exemple :
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  Dans le fichier journal d’exemple C:\\Logs\\OUPermissions.xml, recherchez le résultat d’exécution **\<Opération réussie\>** à la fin de chaque tâche, vérifiez qu’il n’y a aucune erreur, puis fermez le fichier journal. Vous pouvez exécuter l’applet de commande suivante pour tester les autorisations :
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Exemple :
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    > [!NOTE]  
    > Si vous exécutez la préparation de domaine sur le domaine racine de la forêt dans un environnement Active Directory verrouillé, sachez que Lync Server nécessite un accès aux conteneurs Schéma et Configuration dans Active Directory.<br />
    Si l’autorisation d’utilisateur authentifié par défaut est supprimée du conteneur Schéma ou Configuration dans les services de domaine Active Directory, seuls les membres du groupe Administrateurs du schéma (pour le conteneur Schéma) ou du groupe Administrateurs d’entreprise (pour le conteneur Configuration) sont autorisés à accéder au conteneur. Du fait que Setup.exe, les applets de commande Lync Server Management Shell et le Panneau de configuration Lync Server nécessitent un accès à ces conteneurs, la configuration et l’installation des outils d’administration échouent si l’utilisateur qui exécute l’installation n’a pas de droits d’utilisateur équivalents à ceux des membres des groupes Administrateurs du schéma et Administrateurs d’entreprise.<br />
    Pour remédier à cette situation, vous devez octroyer au groupe RTCUniversalGlobalWriteGroup un accès en lecture et en écriture aux conteneurs Schéma et Configuration.
