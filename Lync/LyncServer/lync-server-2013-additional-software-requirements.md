---
title: 'Lync Server 2013 : Autre configuration logicielle requise'
TOCTitle: Autre configuration logicielle requise
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398686(v=OCS.15)
ms:contentKeyID: 49297977
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Autre configuration logicielle requise pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Outre la configuration requise pour le matériel et le système d’exploitation pour les plateformes serveur, Lync Server 2013 requiert l’installation de logiciels supplémentaires sur les serveurs déployés.

> [!NOTE]  
> Pour plus d’informations sur la configuration de plateforme requise pour les serveurs sur lesquels Lync Server est exécuté, reportez-vous à <a href="lync-server-2013-server-hardware-platforms.md">Plateformes matérielles de serveur pour Lync Server 2013</a> et <a href="lync-server-2013-server-and-tools-operating-system-support.md">Prise en charge du système d’exploitation pour le serveur et les outils dans Lync Server 2013</a>. Pour plus d’informations sur la configuration système requise pour les ordinateurs et périphériques clients, reportez-vous à <a href="lync-server-2013-planning-for-clients-and-devices.md">Planification des clients et périphériques dans Lync Server 2013</a> dans la documentation de planification. Pour plus d’informations sur la configuration logicielle requise pour les outils d’administration, reportez-vous à <a href="lync-server-2013-administrative-tools-software-requirements.md">Configuration logicielle requise pour les outils d’administration dans Lync Server 2013</a>.

## Logiciels supplémentaires requis pour tous les rôles serveur internes

Cette section répertorie les logiciels nécessaires pour tous les rôles serveur internes, qui sont des rôles serveur Lync Server, à l’exception du serveur Edge. Les exigences liées à serveurs Edge et à pools de serveurs Edge sont indiquées dans la suite de cette rubrique sous **Logiciels supplémentaires pour les serveurs Edge**.

## Windows PowerShell 3.0

Chaque serveur exécutant Lync Server 2013 doit utiliser la version correcte de Windows PowerShell 3.0. Pour plus d’informations, reportez-vous à [Installation de Windows PowerShell 3.0 pour Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

## Microsoft .NET Framework 4.5

Lync Server requiert Microsoft .NET Framework 4.5 sur tous les rôles serveur internes et sur l’ordinateur où vous exécuterez les outils d’administration Lync Server ou outil de planification Microsoft Lync Server 2013. Pour Lync Server 2013, vous devez installer manuellement sur le serveur la version 64 bits de Microsoft .NET Framework 4.5 avant Lync Server 2013. Pour l’installer manuellement, téléchargez Microsoft .NET 4.5 Framework depuis le Centre de téléchargement Microsoft à l’adresse [http://go.microsoft.com/fwlink/p/?LinkId=268529](http://go.microsoft.com/fwlink/p/?linkid=268529)

## Installation de Microsoft .NET Framework 4.5 sur les serveurs exécutant Windows Server 2012

Si vous installez Microsoft .NET Framework 4.5 sur des serveurs qui exécuteront Lync Server 2013 et Windows Server 2012, vous devez effectuer une étape supplémentaire : après avoir terminé l’installation de .NET Framework 4.5, installez la fonctionnalité Activation HTTP à l’aide du Gestionnaire de serveur.

**Pour installer la fonctionnalité Activation HTTP de .NET Framework 4.5 sur Windows Server 2012**

1.  Dans le menu **Démarrer** , cliquez sur **Programmes** , sur **Outils d’administration** , puis sur **Gestionnaire de serveur** .

2.  Dans le Gestionnaire de serveur, sous **Résumé des fonctionnalités** , sélectionnez **Ajouter des fonctionnalités** .

3.  Développez **.NET Framework 4.5** .

4.  Sélectionnez **Activation de Windows Communication Foundation** si vous ne l’avez pas encore fait, puis sélectionnez **Activation HTTP** .

5.  Cliquez sur **Suivant** et suivez les instructions affichées pour terminer l’installation.

## Windows Identity Foundation

**Windows Identity Foundation** dans Lync Server 2013 nécessite l’installation de Windows Identity Foundation afin de prendre en charge les scénarios d’authentification de serveur à serveur. Windows Server 2008 R2 et Windows Server 2012 nécessitent des procédures différentes pour installer Windows Identify Foundation. Sélectionnez votre système d’exploitation de serveur dans la liste suivante :

  - Windows Server 2008 R2   Pour Windows Server 2008 R2, vérifiez s’il est déjà installé sur votre ordinateur. Pour ce faire accédez à **Ajout/Suppression de programmes** , **Afficher les mises à jour installées** et, sous **Windows** , recherchez l’entrée **Windows Identity Foundation (KB974405)** . Pour plus d’informations sur l’installation de Windows Identity Foundation, reportez-vous à [http://go.microsoft.com/fwlink/p/?linkId=204657](http://go.microsoft.com/fwlink/p/?linkid=204657).

  - Windows Server 2012   Pour Windows Server 2012, vous devez utiliser le **Gestionnaire de serveur** pour installer Windows Identity Foundation. Dans l’**Assistant Ajout de rôles et de fonctionnalités** du Gestionnaire de serveur, sélectionnez **Fonctionnalités** . Sélectionnez **Windows Identity Foundation 3.5** dans la liste. Cliquez sur **Suivant** , puis sur **Installer** .

## Logiciels supplémentaires pour tous les serveurs frontaux et les serveurs Standard Edition

Tous les serveurs frontaux et les serveurs Standard Edition doivent également exécuter les services Internet (IIS) avec certains modules. De plus, tous les serveurs frontaux et Standard Edition sur lesquels sont déployés la conférence, le application de parcage d’appel, les annonces ou Response Groupes doivent exécuter Windows Media Format Runtime.

## Services Internet (IIS)

Les serveurs frontaux et les serveurs Standard Edition doivent exécuter les services Internet (IIS) avec les modules suivants :

  - Contenu statique

  - Document par défaut

  - Erreurs HTTP

  - ASP.NET

  - Extensibilité .NET

  - Extensions ISAPI (Internet Server API)

  - Filtres ISAPI

  - Journalisation HTTP

  - Outils de journalisation

  - Suivi

  - Authentification Windows

  - Filtrage des demandes

  - Compression du contenu statique

  - Compression du contenu dynamique

  - Console de gestion des services Internet (IIS)

  - Scripts et outils de gestion des services Internet (IIS)

  - Authentification anonyme (installée par défaut lors de l’installation des services Internet \[IIS\]).

  - Authentification par mappage de certificat client

## Module d’exécution du format Windows Media et expérience Bureau Windows

**Expérience Bureau Windows** Tous les serveurs frontaux et Standard Edition sur lesquels la conférence sera déployée doivent disposer du module d’exécution du format Windows Media, qui, sauf pour Windows Server 2012 est installé dans le cadre de l’expérience Bureau Windows. Windows Server 2012 requiert Microsoft Media Foundation. Le Module d’exécution du format Windows Media est requis pour exécuter les fichiers Windows Media Audio (.wma) que le parcage d’appel, les applications d’annonces et les applications Response Group lisent pour les annonces et la musique.

Nous vous conseillons d’installer l’expérience Bureau Windows avant d’installer Lync Server 2013. Si Lync Server 2013 ne trouve pas ce logiciel sur le serveur, vous serez invité à l’installer, puis vous devrez redémarrer le serveur pour terminer l’installation.

## Logiciels supplémentaires pour les serveurs frontaux et les serveurs Standard Edition qui exécutent Windows Server 2012

Les serveurs frontaux requièrent .NET 3.5, qui n’est pas installé par défaut sur Windows Server 2012. Pour l’installer, placez votre support d’installation Windows Server 2012 dans le lecteur D et tapez la commande suivante :

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

Pour plus d’informations sur l’installation de .NET 3.5 sur des serveurs exécutant Windows Server 2012, reporte-vous à « Éléments à prendre en compte pour le déploiement de Microsoft .NET Framework 3.5 » à l’adresse <http://go.microsoft.com/fwlink/p/?linkid=275032>.

## Logiciels supplémentaires pour les directeurs

Les directeurs doivent exécuter les services Internet (IIS) avec les modules suivants :

  - Contenu statique

  - Document par défaut

  - Erreurs HTTP

  - ASP.NET

  - Extensibilité .NET

  - Extensions ISAPI (Internet Server API)

  - Filtres ISAPI

  - Journalisation HTTP

  - Outils de journalisation

  - Suivi

  - Authentification Windows

  - Filtrage des demandes

  - Compression du contenu statique

  - Console de gestion des services Internet (IIS)

  - Scripts et outils de gestion des services Internet (IIS)

  - Authentification anonyme (installée par défaut lors de l’installation des services Internet \[IIS\]).

  - Authentification par mappage de certificat client

## Logiciels supplémentaires pour les serveurs frontaux de conversation permanente

Les serveurs frontaux de conversation permanente doivent exécuter MSMQ, qui est un composant de Windows Server.

Pour plus d’informations sur l’activation de MSMQ, [cliquez ici.](http://technet.microsoft.com/en-us/library/cc771474.aspx)

## Logiciels supplémentaires pour les serveurs Edge

Les serveurs Edge nécessitent les composants suivants :

  - Chaque serveur exécutant Lync Server 2013 doit utiliser la version correcte de Windows PowerShell 3.0. Pour plus d’informations, reportez-vous à [Installation de Windows PowerShell 3.0 pour Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

  - Lync Server requiert Microsoft .NET Framework 4.5. Pour Lync Server 2013 installé sur Windows Server 2008 R2, vous devez installer manuellement sur le serveur la version 64 bits de Microsoft .NET Framework 4.5 avant Lync Server 2013. Pour l’installer manuellement, téléchargez Microsoft .NET 4.5 Framework depuis le Centre de téléchargement Microsoft à l’adresse [http://go.microsoft.com/fwlink/p/?LinkId=268529](http://go.microsoft.com/fwlink/p/?linkid=268529)

  - **Windows Identity Foundation** dans Lync Server 2013 nécessite l’installation de Windows Identity Foundation afin de prendre en charge les scénarios d’authentification de serveur à serveur. Windows Server 2008 R2 et Windows Server 2012 nécessitent des procédures différentes pour installer Windows Identify Foundation. Sélectionnez votre système d’exploitation de serveur dans la liste suivante :
    
      - Windows Server 2008 R2  Pour Windows Server 2008 R2, vérifiez s’il est déjà installé sur votre ordinateur. Pour ce faire, accédez à **Ajout/Suppression de programmes** , **Afficher les mises à jour installées** et, sous **Windows** , recherchez l’entrée **Windows Identity Foundation (KB974405)** . Pour plus d’informations sur l’installation de Windows Identity Foundation, reportez-vous à [http://go.microsoft.com/fwlink/p/?LinkID=234777](http://go.microsoft.com/fwlink/p/?linkid=234777).
    
      - Windows Server 2012   Pour Windows Server 2012, vous devez utiliser le **Gestionnaire de serveur** pour installer Windows Identity Foundation. Dans l’**Assistant Ajout de rôles et de fonctionnalités** du Gestionnaire de serveur, sélectionnez **Fonctionnalités** . Sélectionnez **Windows Identity Foundation 3.5** dans la liste. Cliquez sur **Suivant** , puis sur **Installer** .

## N’installez pas les LSP (Layered Socket Provider) sur les serveurs multimédias

N’installez pas de logiciel client Microsoft Internet Security and Acceleration (ISA) Server, ou tout autre logiciel de fournisseurs de service en couche Winsock (LSP), sur les serveurs frontaux ou les serveurs de médiation autonomes. L’installation de ces logiciels peut affecter les performances du trafic multimédia.

## Voir aussi

#### Concepts

[Configuration logicielle requise pour les outils d’administration dans Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)

