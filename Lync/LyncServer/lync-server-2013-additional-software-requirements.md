---
title: 'Lync Server 2013 : Autre configuration logicielle requise'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e21a375fecbd109e108806dc816a9fa3fce81a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a>Autre configuration logicielle requise pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2016-12-08_

Outre le matériel et les exigences en matière de système d’exploitation pour les plates-formes serveur, Lync Server 2013 nécessite l’installation de logiciels supplémentaires sur les serveurs que vous déployez.

<div>


> [!NOTE]  
> Pour plus d’informations sur la configuration requise pour la plateforme pour les serveurs exécutant Lync Server, voir <A href="lync-server-2013-server-hardware-platforms.md">plates-formes matérielles pour Lync server 2013</A> et <A href="lync-server-2013-server-and-tools-operating-system-support.md">serveur et outils pris en charge dans Lync Server 2013</A>. Pour plus d’informations sur la configuration système requise pour les ordinateurs et appareils clients, voir <A href="lync-server-2013-planning-for-clients-and-devices.md">planification des clients et des appareils dans Lync Server 2013</A> dans la documentation de planification. Pour plus d’informations sur la configuration logicielle requise pour les outils d’administration, consultez la <A href="lync-server-2013-administrative-tools-software-requirements.md">configuration logicielle requise pour les outils d’administration dans Lync Server 2013</A>.



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a>Logiciel supplémentaire nécessaire pour tous les rôles de serveur internes

Cette section répertorie les logiciels nécessaires sur tous les rôles de serveur interne, à l’exception des rôles serveur Edge. La configuration requise pour les serveurs Edge et les pools Edge est répertoriée plus loin dans cette rubrique sous **logiciels supplémentaires pour les serveurs de périphérie**.

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Chaque serveur exécutant Lync Server 2013 doit avoir installé la version appropriée de Windows PowerShell 3,0. Pour plus d’informations, consultez [installation de Windows PowerShell 3,0 pour Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Le serveur Lync nécessite Microsoft .NET Framework 4,5 sur tous les rôles de serveur interne et sur les ordinateurs sur lesquels vous allez exécuter les outils d’administration de Lync Server ou Microsoft Lync Server 2013, outil de planification. Pour Lync Server 2013, vous devez installer manuellement l’édition 64 bits de Microsoft .NET Framework 4,5 sur le serveur avant de procéder à l’installation de Lync Server 2013. Pour l’installer manuellement, téléchargez l’infrastructure Microsoft .NET 4,5 à partir du centre de téléchargement Microsoft sur[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a>Installation de Microsoft .NET Framework 4,5 sur des serveurs exécutant Windows Server 2012

Lorsque vous installez Microsoft .NET Framework 4,5 sur des serveurs exécutant Lync Server 2013 et Windows Server 2012, vous devez effectuer une étape supplémentaire. Après avoir installé .NET Framework 4,5, utilisez le gestionnaire de serveur pour installer l’activation HTTP.

**Pour installer l’activation HTTP de .NET 4,5 sur Windows Server 2012**

1.  Dans le menu **Démarrer** , cliquez sur **programmes**, sur **Outils d’administration**, puis sur gestionnaire de **serveur**.

2.  Dans le gestionnaire de serveur, sous **fonctionnalités récapitulatives**, sélectionnez **Ajouter des fonctionnalités**.

3.  Développez **.NET Framework 4,5**.

4.  Sélectionnez **activation WCF** si ce n’est pas déjà fait. Ensuite, sélectionnez **activation http**.

5.  Cliquez sur **suivant** et suivez les invites pour terminer l’installation.

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a>Windows Identity Foundation

**Windows Identity Foundation** dans Lync Server 2013 nécessite l’installation de Windows Identity Foundation afin de prendre en charge les scénarios d’authentification de serveur à serveur. Windows Server 2008 R2 et Windows Server 2012 nécessitent différentes procédures pour installer Windows identify Foundation. Sélectionnez votre système d’exploitation serveur dans la liste suivante:

  - Windows Server 2008 R2 pour Windows Server 2008 R2, vous recherchez s’il a déjà été installé sur votre ordinateur. Pour ce faire, accédez à **Ajout/suppression de programmes**, affichez les **mises à jour installées**et Regardez sous **Windows** pour l’entrée **Windows Identity Foundation (KB974405)**. Pour plus d’informations sur l’installation de Windows [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)Identity Foundation, voir.

  - Windows Server 2012 pour Windows Server 2012, utilisez le **Gestionnaire de serveur** pour installer Windows Identity Foundation. Dans l' **Assistant Ajout de rôles et de fonctionnalités**du gestionnaire de serveur, sélectionnez **fonctionnalités**. Dans la liste, sélectionnez **Windows Identity Foundation 3,5** . Cliquez sur **suivant**, puis sur **installer**.

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a>Logiciels supplémentaires pour tous les serveurs frontaux et les serveurs Standard Edition Server

Tous les serveurs frontaux et les serveurs Standard Edition doivent également exécuter Internet Information Services (IIS) avec certains modules. De plus, tous les serveurs frontaux et les serveurs Standard Edition dans lesquels les conférences, les applications de parc d’appel, les annonces ou les groupes de réponse sont déployés doivent exécuter Windows Media Format Runtime.

<div>

## <a name="internet-information-services-iis"></a>services Internet (IIS)

Les serveurs frontaux et les serveurs Standard Edition doivent exécuter Internet Information Services (IIS), avec les modules suivants:

  - Contenu statique

  - Document par défaut

  - Erreurs HTTP

  - ASP.NET

  - Extensibilité .NET

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

  - Authentification anonyme (installée par défaut lors de l’installation d’IIS)

  - Authentification par mappage de certificat client

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a>Windows Media Format Runtime et expérience de bureau Windows

**Expérience de bureau Windows** Tout serveur frontal et serveur Standard Edition sur lequel les conférences seront déployées doit avoir installé le runtime format Windows Media, qui, à l’exception de Windows Server 2012, est installé dans le cadre de l’expérience de bureau Windows. Windows Server 2012 nécessite Microsoft Media Foundation. Le runtime du format Windows Media est requis pour l’exécution des fichiers Windows Media audio (. WMA) que les applications de parc d’appels, d’annonce et de Response Group sont lues pour les annonces et la musique.

Nous vous recommandons d’installer l’expérience de bureau Windows avant d’installer Lync Server 2013. Si Lync Server 2013 ne trouve pas ce logiciel sur le serveur, il vous invite à l’installer, puis vous devez redémarrer le serveur pour terminer l’installation.

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a>Logiciels supplémentaires pour les serveurs frontaux et les serveurs Standard Edition Server fonctionnant sous Windows Server 2012

Les serveurs frontaux requièrent .NET 3,5, qui n’est pas installé par défaut sur Windows Server 2012. Pour l’installer, placez votre support d’installation de Windows Server 2012 dans le lecteur D et tapez ce qui suit:

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

Pour plus d’informations sur l’installation de .NET 3,5 sur des serveurs exécutant Windows Server 2012, voir «considérations relatives au <https://go.microsoft.com/fwlink/p/?linkid=275032>déploiement de Microsoft .net Framework 3,5» à l’adresse.

</div>

<div>

## <a name="additional-software-for-directors"></a>Logiciels supplémentaires pour les directeurs

Les directeurs doivent exécuter Internet Information Services (IIS), avec les modules suivants:

  - Contenu statique

  - Document par défaut

  - Erreurs HTTP

  - ASP.NET

  - Extensibilité .NET

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

  - Authentification anonyme (installée par défaut lors de l’installation d’IIS)

  - Authentification par mappage de certificat client

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a>Logiciel supplémentaire pour les serveurs front end chat persistants

Les serveurs front-end chat permanents doivent exécuter Message Queuing (également appelé MSMQ), qui est un composant de Windows Server.

Pour plus d’informations sur l’activation de MSMQ, [cliquez ici.](https://technet.microsoft.com/en-us/library/cc771474.aspx)

</div>

<div>

## <a name="additional-software-for-edge-servers"></a>Logiciels supplémentaires pour les serveurs de périphérie

Les serveurs Edge nécessitent le logiciel suivant:

  - Chaque serveur exécutant Lync Server 2013 doit avoir installé la version appropriée de Windows PowerShell 3,0. Pour plus d’informations, consultez [installation de Windows PowerShell 3,0 pour Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

  - Lync Server nécessite Microsoft .NET Framework 4,5. Pour Lync Server 2013 installé sur Windows Server 2008 R2, vous devez installer manuellement l’édition 64 bits de Microsoft .NET Framework 4,5 sur le serveur avant d’installer Lync Server 2013. Pour l’installer manuellement, téléchargez l’infrastructure Microsoft .NET 4,5 à partir du centre de téléchargement Microsoft sur[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

  - **Windows Identity Foundation** dans Lync Server 2013 nécessite l’installation de Windows Identity Foundation afin de prendre en charge les scénarios d’authentification de serveur à serveur. Windows Server 2008 R2 et Windows Server 2012 nécessitent différentes procédures pour installer Windows identify Foundation. Sélectionnez votre système d’exploitation serveur dans la liste suivante:
    
      - Windows Server 2008 R2 pour Windows Server 2008 R2, vous recherchez s’il a déjà été installé sur votre ordinateur. Pour ce faire, accédez à **Ajout/suppression de programmes**, affichez les **mises à jour installées**et Regardez sous **Windows** pour l’entrée **Windows Identity Foundation (KB974405)**. Pour plus d’informations sur l’installation de Windows [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)Identity Foundation, voir.
    
      - Windows Server 2012 pour Windows Server 2012, utilisez le **Gestionnaire de serveur** pour installer Windows Identity Foundation. Dans l' **Assistant Ajout de rôles et de fonctionnalités**du gestionnaire de serveur, sélectionnez **fonctionnalités**. Dans la liste, sélectionnez **Windows Identity Foundation 3,5** . Cliquez sur **suivant**, puis sur **installer**.

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a>Ne pas installer les fournisseurs de Socket Layer sur les serveurs multimédias

N’installez aucun logiciel client Microsoft Internet Security and Acceleration (ISA) Server, ou tout autre logiciel de fournisseur de services de couche Winsock (LSP) sur un serveur frontal ou un serveur de médiation autonome. L’installation de ce logiciel peut entraîner de mauvaises performances du trafic multimédia.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration logicielle requise pour les outils d’administration dans Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

