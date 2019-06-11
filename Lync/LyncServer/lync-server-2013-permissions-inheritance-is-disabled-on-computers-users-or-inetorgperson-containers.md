---
title: 'Lync Server 2013 : Désactivation de l’héritage des autorisations sur les conteneurs des objets Ordinateur, Utilisateur ou InetOrgPerson'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48185348
ms.date: 12/19/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73692539fb5dda38446ffddccbe35c8d366e2d67
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a>Désactivation de l’héritage des autorisations sur les conteneurs des objets Ordinateur, Utilisateur ou InetOrgPerson dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-12-19_

Dans les services de domaine Active Directory (AD DS) verrouillés, les utilisateurs et les objets d’ordinateur sont souvent placés dans des unités d’organisation spécifiques (UO) avec l’héritage des autorisations désactivé pour sécuriser la délégation d’administration et permettre l’utilisation des objets de stratégie de groupe (GPO). pour appliquer les stratégies de sécurité.

Préparation du domaine et activation du serveur définissez les entrées de contrôle d’accès (ACE) requises par Lync Server 2013. Lorsque l’héritage des autorisations est désactivé, les groupes de sécurité du serveur Lync ne peuvent pas hériter de ces ACE. Lorsque ces autorisations ne sont pas héritées, les groupes de sécurité du serveur Lync ne peuvent pas accéder aux paramètres, et les deux problèmes suivants peuvent se produire:

  - Pour gérer les utilisateurs, les InetOrgPersons, les contacts et les serveurs, les groupes de sécurité du serveur Lync requièrent des entrées ACE définies par la procédure de préparation du domaine sur les jeux de propriétés de chaque utilisateur, de communication en temps réel (RTC), de recherche d’utilisateurs RTC et d’informations publiques. . Lorsque l’héritage des autorisations est désactivé, les groupes de sécurité n’héritent pas de ces ACE et ne peuvent pas gérer les serveurs ou les utilisateurs.

  - Pour détecter les serveurs et les pools, les serveurs exécutant Lync Server dépendent des ACE définies par l’activation sur les objets liés aux ordinateurs, dont le conteneur et l’objet serveur Microsoft. Lorsque l’héritage des autorisations est désactivé, les groupes de sécurité, les serveurs et les pools n’héritent pas de ces ACE et ne peuvent pas bénéficier de ces ACE.

Pour résoudre ces problèmes, Lync Server fournit l’applet **de passe Grant-CsOuPermission** . Ce cmdlet définit les ACE serveur Lync requis directement sur un conteneur et des unités d’organisation et des objets au sein du conteneur ou de l’unité d’organisation.

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a>Définir des autorisations pour les objets utilisateur, InetOrgPerson et contact après l’exécution de la préparation du domaine

Dans un environnement Active Directory verrouillé dans lequel l’héritage des autorisations est désactivé, la préparation du domaine ne définit pas les ACE nécessaires sur les conteneurs ou les unités d’organisation qui contiennent des utilisateurs ou des objets InetOrgPerson au sein du domaine. Dans ce cas, vous devez exécuter l’applet de passe **Grant-CsOuPermission** sur chaque conteneur ou unité d’organisation qui comporte des objets utilisateur ou InetOrgPerson pour lesquels l’héritage des autorisations est désactivé. Si vous disposez d’une topologie de forêt centrale, vous devez également effectuer cette procédure sur les conteneurs ou les unités d’organisation qui contiennent des objets de contact. Pour plus d’informations sur les topologies de forêt centralisées, voir [topologies Active Directory prises en charge dans Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) dans la documentation relative à la prise en charge. Le paramètre typeobjet spécifie le type d’objet. Le paramètre UO spécifie l’unité d’organisation.

Cette applet de demande ajoute les entrées ACE requises directement dans les conteneurs ou UO spécifiques et dans le conteneur. Si l’unité d’organisation sur laquelle cette commande est exécutée possède des unités d’organisation enfants avec des objets utilisateur ou InetOrgPerson, les autorisations ne sont pas appliquées sur celles-ci. Vous devez exécuter la commande sur chaque UO enfant individuellement. Il s’agit d’un scénario courant avec des déploiements d’hébergement Lync, par exemple, des UO parentes, DC = CONTOSO, DC = LOCAL et Child UO = premier client, UO = clients OCS, DC = CONTOSO, DC = LOCAL.

Pour exécuter cette cmdlet, vous devez disposer des droits d’utilisateur pour l’appartenance au groupe administrateurs de domaine. Si les entrées ACE de l’utilisateur authentifié ont également été supprimées de l’environnement verrouillé, vous devez accorder à ce compte des ACE d’accès en lecture sur les conteneurs appropriés ou les UO dans le domaine racine de la forêt, comme décrit dans la section [les autorisations des utilisateurs authentifiés sont supprimées dans Lync. Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) ou utiliser un compte membre du groupe administrateurs d’entreprise.

**Pour définir les entrées ACE requises pour les objets utilisateur, InetOrgPerson et contact**

1.  Connectez-vous à un ordinateur joint au domaine avec un compte membre du groupe administrateurs de domaine ou qui dispose de droits d’utilisateur équivalents.

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez :
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Si vous ne spécifiez pas le paramètre domain, la valeur par défaut est le domaine local.
    
    Par exemple :
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  Dans le fichier journal, recherchez le résultat d’exécution ** \<réussie\> ** à la fin de chaque tâche pour vérifier que les autorisations ont été définies, puis fermez la fenêtre du journal. Vous pouvez utiliser la commande suivante pour déterminer si les autorisations ont été définies:
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    Par exemple :
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a>Définir des autorisations pour les objets ordinateur après l’exécution de la préparation du domaine

Dans un environnement Active Directory verrouillé dans lequel l’héritage des autorisations est désactivé, la préparation du domaine ne définit pas les ACE nécessaires sur les conteneurs ou les unités d’organisation qui contiennent des objets d’ordinateur au sein du domaine. Dans ce cas, vous devez exécuter l’applet de passe **Grant-CsOuPermission** sur chaque conteneur ou unité d’organisation qui comporte des ordinateurs exécutant Lync Server et sur lequel l’héritage des autorisations est désactivé. Le paramètre typeobjet spécifie le type d’objet.

Cette procédure ajoute les entrées ACE requises directement sur les conteneurs spécifiés.

Pour exécuter cette cmdlet, vous devez disposer des droits d’utilisateur pour l’appartenance au groupe administrateurs de domaine. Si les ACE des utilisateurs authentifiés ont été supprimées, vous devez accorder ce compte aux entrées ACE d’accès en lecture sur les conteneurs pertinents dans le domaine racine de la forêt, comme décrit dans la section [les autorisations des utilisateurs authentifiés sont supprimées dans Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) ou utiliser un compte qui est a membre du groupe administrateurs d’entreprise.

**Pour définir les entrées ACE requises pour les objets ordinateur**

1.  Connectez-vous à l’ordinateur du domaine avec un compte membre du groupe administrateurs de domaine ou qui dispose de droits d’utilisateur équivalents.

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez :
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    Si vous ne spécifiez pas le paramètre domain, la valeur par défaut est le domaine local.
    
    Par exemple :
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  Dans l’exemple de fichier journal C\\:\\enregistre OUPermissions. xml, vous devez chercher ** \<le\> ** résultat d’exécution réussie à la fin de chaque tâche et vérifier qu’il n’y a aucune erreur, puis fermer le journal. Vous pouvez exécuter l’applet de commande suivante pour tester les autorisations:
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Par exemple :
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > Si vous exécutez une préparation de domaine sur le domaine racine de la forêt dans un environnement Active Directory verrouillé, sachez que Lync Server doit avoir accès au schéma Active Directory et aux conteneurs de configuration.<BR>Si l’autorisation utilisateur authentifié par défaut est supprimée du schéma ou des conteneurs de configuration dans&nbsp;AD DS, seuls les membres du groupe administrateurs de schéma (pour le conteneur de schéma) ou des administrateurs d’entreprise (pour le conteneur de configuration) sont autorisés à Accédez au conteneur donné. Dans la mesure où les applets de commande Setup. exe, Lync Server Management Shell et le panneau de configuration de Lync Server requièrent l’accès à ces conteneurs, la configuration et l’installation des outils d’administration échouent sauf si l’utilisateur qui exécute l’installation dispose de droits d’utilisateur équivalents au schéma Appartenance au groupe administrateurs et administrateurs d’entreprise.<BR>Pour remédier à ce problème, vous devez accorder au groupe RTCUniversalGlobalWriteGroup l’accès en lecture, en écriture au schéma et aux conteneurs de configuration.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

