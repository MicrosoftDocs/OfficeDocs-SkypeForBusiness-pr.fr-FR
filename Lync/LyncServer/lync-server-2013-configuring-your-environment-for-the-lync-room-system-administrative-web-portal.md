---
title: "Lync Server 2013 : Conf. env. pour le portail web d’adm. de Lync Room System"
TOCTitle: Configuration de votre environnement pour le portail web d’administration de Lync Room System
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn436325(v=OCS.15)
ms:contentKeyID: 59602868
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de votre environnement Lync Server 2013 pour le portail web d’administration de Lync Room System

 

_**Dernière rubrique modifiée :** 2016-12-08_

Pour utiliser le portail web d’administration de Lync Room System (LRS), vous devez remplir les conditions préalables suivantes.

> [!IMPORTANT]  
> Si le serveur est configuré avec les authentifications Kerberos et NTLM, et que LRS est en cours d’exécution sur un ordinateur non associé au domaine, l’authentificaton Kerberos échouera et l’utilisateur ne pourra pas visualiser le statut de LRS sur le portail d’administration. Pour résoudre ce problème, configurez le serveur avec l’authentification NTLM, ou avec les authentifications NTLM et TLS-DSK (sans Kerberos), ou associez l’ordinateur LRS au domaine.

1.  Installez les mises à jour cumulatives de juillet 2013 pour Lync Server 2013 dans la topologie Lync Server.
    
    Pour obtenir la mise à jour ou consulter son contenu, reportez-vous à [Updates for Lync Server 2013 (Mises à jour pour Lync Server 2013)](http://go.microsoft.com/fwlink/p/?linkid=323959).

2.  Créez un utilisateur Active Directory activé pour SIP.
    
    Le portail web d’administration de LRS utilise les informations d’identification suivantes pour demander des informations auprès de Lync Server. Il est recommandé d’utiliser le nom d’utilisateur LRSApp.

3.  Créez un groupe de sécurité Active Directory nommé LRSSupportAdminGroup.
    
    Créez le groupe avec une étendue globale et le type Sécurité. Les utilisateurs activés pour SIP ajoutés à ce groupe seront autorisés à afficher la liste des pièces et à exécuter certaines commandes, telles que la collecte de journaux.

4.  Créez un groupe de sécurité Active Directory nommé LRSFullAccessAdminGroup.
    
    Créez le groupe avec une étendue globale et le type Sécurité. Les utilisateurs activés pour SIP ajoutés à ce groupe sont autorisés à utiliser toutes les fonctionnalités du portail d’administration.
    
     
    
    ![Liste des groupes d’administrateurs avec rôle de groupe de sécurité](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "Liste des groupes d’administrateurs avec rôle de groupe de sécurité")  
    
     

5.  Ajoutez LRSFullAccessAdminGroup comme membre du groupe LRSSupportAdminGroup.
    
    ![Page des membres des propriétés LRSSupportAdminGroup](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "Page des membres des propriétés LRSSupportAdminGroup")  
    
     

6.  Créez un utilisateur Active Directory activé pour SIP avec le nom LRSSupport. Ajoutez cet utilisateur au groupe LRSSupportAdminGroup.
    
    ![Page des membres des propriétés LRSSupportAdminGroup](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "Page des membres des propriétés LRSSupportAdminGroup")  
    
     

7.  Installez ASP.NET MVC 4 pour Visual Studio 2010 SP1 et Visual Web Developer 2010 SP1 à partir du Centre de téléchargement Microsoft via la page [http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967).

