---
title: Installation du portail web d’administration de Lync Room System
TOCTitle: Installation du portail web d’administration de Lync Room System
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn436326(v=OCS.15)
ms:contentKeyID: 59602875
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installation du portail web d’administration de Lync Room System

 

_**Dernière rubrique modifiée :** 2016-12-08_

Vous pouvez télécharger le portail web d’administration de Microsoft Lync Room System à partir du Centre de téléchargement Microsoft à l’adresse [http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044).

Pour installer le portail web d’administration de Lync Room System, procédez comme suit.

1.  Configurez le port de l’application approuvée en exécutant l’applet de commande suivante dans Lync Server Management Shell :
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  Pour installer le portail d’administration de Lync Room System, téléchargez **LyncRoomAdminPortal.exe**, puis exécutez-le en tant qu’administrateur.

3.  Ouvrez le fichier Web.config à partir de l’emplacement suivant :
    
    %Program Files%\\Microsoft Lync Server 2013\\Web Components\\Meeting Room Portal\\Int\\Handler\\

4.  Dans le fichier Web.Config, définissez la valeur PortalUserName sur le nom d’utilisateur créé à l’étape 2 sous la section « Configuration des éléments requis pour le portail d’administration de Lync Room System » (le nom recommandé dans l’étape est LRSApp) :
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  Comme le portail d’administration de LRS est une application approuvée, vous n’avez pas besoin d’indiquer le mot de passe dans la configuration du portail. Si cet utilisateur utilise un autre serveur d’inscriptions que le serveur d’inscriptions local, vous devez le spécifier en ajoutant la ligne suivante dans le fichier Web.Config :
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  Si le port utilisé n’est pas le port 5061, ajoutez la ligne suivante dans le fichier Web.Config :
    
        <add key="PortalUserRegistrarPort" value="5061" />

## Vérification de l’installation du portail web d’administration de Lync Room System

Pour vérifier l’installation du portail web d’administration de Lync Room System, procédez comme suit :


1.  Sur un serveur frontal, accédez à l’URL suivante :
    
    https://\<fe-server\>/lrs
    
    Aucune erreur ne doit s’afficher, comme dans l’image suivante :
    
    ![Écran Connexion au portail d’administration Lync Room System](images/Dn743660.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Écran Connexion au portail d’administration Lync Room System")

2.  Si aucune erreur ne s’affiche, essayez d’accéder à l’URL suivante à partir d’un autre ordinateur dans la topologie :
    
    https://\<fe-server\>/lrs
    
    Pour accéder à la page, vous devez ajouter les enregistrements DNS comme décrit dans la rubrique « Required DNS Records for Automatic Client Sign-In » (Enregistrements DNS requis pour la connexion automatique du client) à l’adresse [http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056).

