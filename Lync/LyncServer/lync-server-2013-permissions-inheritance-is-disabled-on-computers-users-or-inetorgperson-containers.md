---
title: 'Lync Server 2013 : l’héritage des autorisations est désactivé sur les conteneurs des ordinateurs, des utilisateurs ou des InetOrgPerson'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48185348
ms.date: 12/19/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6f0ac6b7614da844a35f97070b61f1b074a4367
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a>L’héritage des autorisations est désactivé sur les conteneurs ordinateurs, utilisateurs ou InetOrgPerson dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-12-19_

Dans les services de domaine Active Directory verrouillés, les utilisateurs et les objets ordinateur sont souvent placés dans des unités d’organisation (UO) spécifiques dont l’héritage des autorisations est désactivé pour aider à sécuriser la délégation d’administration et pour permettre l’utilisation des objets de stratégie de groupe (GPO). pour appliquer des stratégies de sécurité.

Préparation de domaine et activation de serveur définissez les entrées de contrôle d’accès (ACE) requises par Lync Server 2013. Lorsque l’héritage des autorisations est désactivé, les groupes de sécurité Lync Server ne peuvent pas hériter de ces ACE. Lorsque ces autorisations ne sont pas héritées, les groupes de sécurité Lync Server ne peuvent pas accéder aux paramètres et les deux problèmes suivants se produisent :

  - Pour administrer les utilisateurs, les InetOrgPersons et les contacts, et pour exploiter les serveurs, les groupes de sécurité Lync Server nécessitent des ACE définies par la procédure de préparation du domaine sur les jeux de propriétés de chaque utilisateur, les communications en temps réel (RTC), la recherche d’utilisateur RTC et les informations publiques. . Quand l’héritage des autorisations est désactivé, les groupes de sécurité n’héritent pas ces entrées de contrôle d’accès et ne peuvent pas gérer les serveurs ou les utilisateurs.

  - Pour détecter les serveurs et les pools, les serveurs exécutant Lync Server s’appuient sur les ACE définies par l’activation sur les objets liés à l’ordinateur, y compris le conteneur Microsoft et l’objet serveur. Quand l’héritage des autorisations est désactivé, les groupes de sécurité, les serveurs et les pools n’héritent pas de ces entrées de contrôle d’accès et ne peuvent pas les exploiter.

Pour résoudre ces problèmes, Lync Server fournit l’applet **de commande Grant-CsOuPermission** . Cette applet de commande définit les ACE Lync Server requises directement sur un conteneur et des unités d’organisation spécifiés, ainsi que sur les objets dans le conteneur ou l’unité d’organisation.

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a>Définir des autorisations sur les objets Utilisateur, InetOrgPerson et Contact après exécution de la préparation du domaine

Dans un environnement Active Directory verrouillé dans lequel l’héritage des autorisations est désactivé, la préparation du domaine ne définit pas les entrées de contrôle d’accès nécessaires sur les conteneurs ou les unités d’organisation abritant des objets Utilisateur ou InetOrgPerson à l’intérieur du domaine. Dans ce cas, vous devez exécuter l’applet de commande **Grant-CsOuPermission** sur chaque conteneur ou unité d’organisation contenant les objets Utilisateur ou InetOrgPerson pour lesquels l’héritage des autorisations est désactivé. Si vous avez déployé une topologie de forêt centrale, vous devez également exécuter cette procédure sur les conteneurs ou les unités d’organisation qui détiennent des objets Contact. Pour plus d’informations sur les topologies de forêt centrale, voir [topologies Active Directory prises en charge dans Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) dans la documentation de prise en charge. Le paramètre ObjectType précise le type d’objet. Le paramètre OU spécifie l’unité d’organisation.

Cette applet de commande ajoute directement les entrées de contrôle d’accès requises sur les conteneurs ou les unités d’organisation spécifiées et les objets Utilisateur et InetOrgPerson qu’ils contiennent. Si l’unité d’organisation sur laquelle cette commande est exécutée comporte des unités d’organisation enfants avec des objets utilisateur ou InetOrgPerson, les autorisations ne sont pas appliquées sur ces unités. Vous devrez exécuter la commande sur chaque unité d’organisation enfant individuellement. Il s’agit d’un scénario courant avec les déploiements d’hébergement Lync, par exemple l’unité d’organisation parente, les clients OCS, DC = CONTOSO, DC = LOCAL et Child OU = Tenant1, OU = OCS clients, DC = CONTOSO, DC = LOCAL.

Pour exécuter cette applet de commande, vous devez bénéficier de droits d’utilisateur identiques à ceux utilisés en tant que membre du groupe Administrateurs de domaine. Si les ACE de l’utilisateur authentifié ont également été supprimées dans l’environnement verrouillé, vous devez accorder à ce compte les ACE accès en lecture sur les conteneurs ou unités d’organisation appropriés dans le domaine racine de la forêt, comme décrit dans la rubrique les [autorisations des utilisateurs authentifiés sont supprimées dans Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) ou utilisez un compte membre du groupe administrateurs de l’entreprise.

**Pour définir les entrées de contrôle d’accès requises pour les objets Utilisateur, InetOrgPerson et Contact**

1.  Ouvrez une session sur un ordinateur lié au domaine en utilisant un compte qui est membre du groupe Administrateurs de domaine ou doté de droits d’utilisateur équivalents.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Générer
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.
    
    Par exemple :
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  Dans le fichier journal, recherchez résultats ** \<de\> ** l’exécution réussie à la fin de chaque tâche pour vérifier que les autorisations ont été définies, puis fermez la fenêtre du journal. Vous pouvez également exécuter la commande suivante pour déterminer si les autorisations ont été définies :
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    Par exemple :
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a>Définir des autorisations sur les objets Ordinateur après exécution de la préparation du domaine

Dans un environnement Active Directory verrouillé dans lequel l’héritage des autorisations est désactivé, la préparation du domaine ne définit pas les entrées de contrôle d’accès nécessaires sur les conteneurs ou les unités d’organisation abritant des objets Ordinateur à l’intérieur du domaine. Dans ce cas, vous devez exécuter l’applet de commande **Grant-CsOuPermission** sur chaque conteneur ou unité d’organisation dont les ordinateurs exécutent Lync Server et où l’héritage des autorisations est désactivé. Le paramètre ObjectType précise le type d’objet.

Cette procédure ajoute directement les entrées de contrôle d’accès requises sur les conteneurs spécifiés.

Pour exécuter cette applet de commande, vous devez bénéficier de droits d’utilisateur identiques à ceux utilisés en tant que membre du groupe Administrateurs de domaine. Si les ACE de l’utilisateur authentifié ont également été supprimées, vous devez accorder à ce compte les ACE accès en lecture-écriture sur les conteneurs appropriés dans le domaine racine de la forêt, comme décrit dans la rubrique les [autorisations des utilisateurs authentifiés sont supprimées dans Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) ou utilisez un compte membre du groupe administrateurs de l’entreprise.

**Pour configurer les entrées de contrôle d’accès requises pour les objets Ordinateur**

1.  Ouvrez une session sur l’ordinateur du domaine en utilisant un compte qui est membre du groupe Administrateurs de domaine ou doté de droits d’utilisateur équivalents.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Générer
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.
    
    Par exemple :
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  Dans l’exemple de fichier journal C\\:\\enregistre OUPermissions. xml, vous devez rechercher les résultats de l’exécution ** \<réussie\> ** à la fin de chaque tâche et vérifier qu’il n’y a pas d’erreurs, puis fermer le journal. Vous pouvez exécuter l’applet de commande suivante pour tester les autorisations :
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Par exemple :
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > Si vous exécutez une préparation de domaine sur le domaine racine de la forêt dans un environnement Active Directory verrouillé, sachez que Lync Server doit avoir accès aux conteneurs de schéma et de configuration Active Directory.<BR>Si l’autorisation utilisateur authentifié par défaut est supprimée du schéma ou des conteneurs de configuration dans&nbsp;AD DS, seuls les membres du groupe administrateurs du schéma (pour le conteneur de schéma) ou du groupe administrateurs de l’entreprise (pour le conteneur de configuration) sont autorisés à accéder au conteneur donné. Étant donné que Setup. exe, les cmdlets de Lync Server Management Shell et le panneau de configuration Lync Server nécessitent un accès à ces conteneurs, la configuration et l’installation des outils d’administration échouent, sauf si l’utilisateur qui exécute l’installation dispose de droits d’utilisateur équivalents au schéma. Appartenance au groupe administrateurs et administrateurs de l’entreprise.<BR>Pour remédier à cette situation, vous devez octroyer au groupe RTCUniversalGlobalWriteGroup un accès en lecture et en écriture aux conteneurs Schéma et Configuration.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

