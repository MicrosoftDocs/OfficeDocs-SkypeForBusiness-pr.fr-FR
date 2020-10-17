---
title: 'Lync Server 2013 : configuration logicielle requise supplémentaire'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a4a0c2e200c779d87a13c08eada968b27a7447f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521231"
---
# <a name="additional-software-requirements-for-lync-server-2013"></a>Configuration logicielle requise supplémentaire pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-12-08_

Outre le matériel et le système d’exploitation requis pour les plateformes serveur, Lync Server 2013 nécessite l’installation de logiciels supplémentaires sur les serveurs que vous déployez.

<div>


> [!NOTE]  
> Pour plus d’informations sur la configuration requise pour la plateforme pour les serveurs exécutant Lync Server, consultez la rubrique <A href="lync-server-2013-server-hardware-platforms.md">Server Hardware Platforms for Lync server 2013</A> et <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and Tools Operating System Support in Lync Server 2013</A>. Pour plus d’informations sur la configuration système requise pour les ordinateurs clients et les périphériques, voir <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and Devices in Lync Server 2013</A> dans la documentation de planification. Pour plus d’informations sur la configuration logicielle requise pour les outils d’administration, consultez la rubrique <A href="lync-server-2013-administrative-tools-software-requirements.md">configuration logicielle requise pour les outils d’administration dans Lync Server 2013</A>.



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a>Logiciels supplémentaires nécessaires pour tous les rôles serveur internes

Cette section répertorie les logiciels nécessaires sur tous les rôles serveur internes, qui sont tous les rôles serveur Lync Server, à l’exception du serveur Edge. La configuration requise pour les serveurs Edge et les pools de serveurs Edge est indiquée plus loin dans cette rubrique sous **logiciels supplémentaires pour les serveurs Edge**.

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

La version correcte de Windows PowerShell 3,0 doit être installée sur chaque serveur exécutant Lync Server 2013. Pour plus d’informations, consultez la rubrique [installation de Windows PowerShell 3,0 pour Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Lync Server requiert Microsoft .NET Framework 4,5 sur tous les rôles serveur internes et sur tout ordinateur sur lequel vous allez exécuter les outils d’administration Lync Server ou l’outil de planification Microsoft Lync Server 2013. Pour Lync Server 2013, vous devez installer manuellement l’édition 64 bits de Microsoft .NET Framework 4,5 sur le serveur avant d’installer Lync Server 2013. Pour l’installer manuellement, téléchargez Microsoft .NET 4,5 Framework à partir du centre de téléchargement Microsoft à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a>Installation de Microsoft .NET Framework 4,5 sur des serveurs exécutant Windows Server 2012

Lorsque vous installez Microsoft .NET Framework 4,5 sur des serveurs qui exécuteront Lync Server 2013 et Windows Server 2012, vous devez effectuer une étape supplémentaire. Après avoir installé .NET Framework 4,5, utilisez le gestionnaire de serveur pour installer l’activation HTTP.

**Pour installer .NET 4,5 HTTP activation sur Windows Server 2012**

1.  Dans le menu **Démarrer** , cliquez sur **programmes**, sur **Outils d’administration**, puis sur gestionnaire de **serveur**.

2.  Dans le gestionnaire de serveur, sous **Résumé des fonctionnalités**, sélectionnez **Ajouter des fonctionnalités**.

3.  Développez **.NET Framework 4,5**.

4.  Sélectionnez **activation WCF** si elle n’est pas déjà sélectionnée. Ensuite, sélectionnez **activation http**.

5.  Cliquez sur **suivant** et suivez les invites pour terminer l’installation.

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a>Windows Identity Foundation

**Windows Identity Foundation** dans Lync Server 2013 nécessite l’installation de Windows Identity Foundation afin de prendre en charge les scénarios d’authentification serveur à serveur. Windows Server 2008 R2 et Windows Server 2012 nécessitent des procédures différentes pour installer Windows identify Foundation. Sélectionnez votre système d’exploitation serveur dans la liste suivante :

  - Windows Server 2008 R2 pour Windows Server 2008 R2, vérifiez si elle a déjà été installée sur votre ordinateur. Pour ce faire, accédez à **Ajout/suppression de programmes**, **Affichez les mises à jour installées**et Regardez sous **Windows** pour l’entrée **Windows Identity Foundation (KB974405)**. Pour plus d’informations sur l’installation de Windows Identity Foundation, reportez-vous à [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) .

  - Windows Server 2012 pour Windows Server 2012, vous utilisez le **Gestionnaire de serveur** pour installer Windows Identity Foundation. Dans l' **Assistant Ajout de rôles et de fonctionnalités**du gestionnaire de serveur, sélectionnez **fonctionnalités**. Sélectionnez **Windows Identity Foundation 3,5** dans la liste. Cliquez sur **suivant**, puis sur **installer**.

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a>Logiciels supplémentaires pour tous les serveurs frontaux et les serveurs Standard Edition

Tous les serveurs frontaux et les serveurs Standard Edition Server doivent également exécuter les services Internet (IIS) avec certains modules. De plus, tous les serveurs frontaux et les serveurs Standard Edition Server sur lesquels les conférences, les applications de parcage d’appel, les annonces ou les groupes Response Group doivent exécuter Windows Media Format Runtime.

<div>

## <a name="internet-information-services-iis"></a>Internet Information Services (IIS)

Les serveurs frontaux et les serveurs Standard Edition Server doivent exécuter les services Internet (IIS), avec les modules suivants :

  - Contenu statique

  - Document par défaut

  - Erreurs HTTP

  - ASP.NET

  - Extensibilité .NET

  - Extensions ISAPI (Internet Server API)

  - Filtres ISAPI

  - Journalisation HTTP

  - Outils de journalisation

  - Analyzer

  - Authentification Windows

  - Filtrage des demandes

  - Compression du contenu statique

  - Compression du contenu dynamique

  - Console de gestion IIS

  - Scripts et outils de gestion IIS

  - Authentification anonyme (installée par défaut lors de l’installation d’IIS.)

  - Authentification par mappage de certificat client

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a>Windows Media Format Runtime et expérience de bureau Windows

**Expérience de bureau Windows** Tous les serveurs frontaux et les serveurs Standard Edition Server sur lesquels les conférences seront déployées doivent avoir installé le runtime de format Windows Media, qui, à l’exception de Windows Server 2012, est installé dans le cadre de l’expérience de bureau Windows. Windows Server 2012 nécessite Microsoft Media Foundation. Le module d’exécution du format Windows Media est nécessaire pour exécuter les fichiers audio Windows Media (.wma) qui sont lus pour les annonces et la musique par les applications de parcage d’appel, d’annonce et Response Group.

Nous vous recommandons d’installer expérience Bureau Windows avant d’installer Lync Server 2013. Si Lync Server 2013 ne trouve pas ce logiciel sur le serveur, il vous invite à l’installer, puis vous devez redémarrer le serveur pour terminer l’installation.

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a>Logiciels supplémentaires pour les serveurs frontaux et les serveurs Standard Edition s’exécutant sur Windows Server 2012

Les serveurs frontaux nécessitent .NET 3,5, qui n’est pas installé par défaut sur Windows Server 2012. Pour l’installer, placez le support d’installation de Windows Server 2012 dans le lecteur D, puis tapez ce qui suit :

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

Pour plus d’informations sur l’installation de .NET 3,5 sur des serveurs exécutant Windows Server 2012, voir « considérations pour le déploiement de Microsoft .NET Framework 3,5 » à l’adresse <https://go.microsoft.com/fwlink/p/?linkid=275032> .

</div>

<div>

## <a name="additional-software-for-directors"></a>Logiciels supplémentaires pour les directeurs

Les directeurs doivent exécuter les services Internet (IIS), avec les modules suivants :

  - Contenu statique

  - Document par défaut

  - Erreurs HTTP

  - ASP.NET

  - Extensibilité .NET

  - Extensions ISAPI (Internet Server API)

  - Filtres ISAPI

  - Journalisation HTTP

  - Outils de journalisation

  - Analyzer

  - Authentification Windows

  - Filtrage des demandes

  - Compression du contenu statique

  - Console de gestion IIS

  - Scripts et outils de gestion IIS

  - Authentification anonyme (installée par défaut à l’installation d’IIS).

  - Authentification par mappage de certificat client

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a>Logiciels supplémentaires pour les serveurs frontaux de conversation permanente

Les serveurs frontaux de conversation permanente doivent exécuter Message Queuing (également appelé MSMQ), qui est un composant de Windows Server.

Pour plus d’informations sur l’activation de MSMQ, [cliquez ici.](https://technet.microsoft.com/library/cc771474.aspx)

</div>

<div>

## <a name="additional-software-for-edge-servers"></a>Logiciels supplémentaires pour les serveurs Edge

Les serveurs Edge requièrent les logiciels suivants :

  - La version correcte de Windows PowerShell 3,0 doit être installée sur chaque serveur exécutant Lync Server 2013. Pour plus d’informations, consultez la rubrique [installation de Windows PowerShell 3,0 pour Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

  - Lync Server requiert Microsoft .NET Framework 4,5. Pour Lync Server 2013 installé sur Windows Server 2008 R2, vous devez installer manuellement l’édition 64 bits de Microsoft .NET Framework 4,5 sur le serveur avant d’installer Lync Server 2013. Pour l’installer manuellement, téléchargez Microsoft .NET 4,5 Framework à partir du centre de téléchargement Microsoft à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

  - **Windows Identity Foundation** dans Lync Server 2013 nécessite l’installation de Windows Identity Foundation afin de prendre en charge les scénarios d’authentification serveur à serveur. Windows Server 2008 R2 et Windows Server 2012 nécessitent des procédures différentes pour installer Windows identify Foundation. Sélectionnez votre système d’exploitation serveur dans la liste suivante :
    
      - Windows Server 2008 R2 pour Windows Server 2008 R2, vérifiez si elle a déjà été installée sur votre ordinateur. Pour ce faire, accédez à **Ajout/suppression de programmes**, **Affichez les mises à jour installées**et Regardez sous **Windows** pour l’entrée **Windows Identity Foundation (KB974405)**. Pour plus d’informations sur l’installation de Windows Identity Foundation, reportez-vous à [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) .
    
      - Windows Server 2012 pour Windows Server 2012, vous utilisez le **Gestionnaire de serveur** pour installer Windows Identity Foundation. Dans l' **Assistant Ajout de rôles et de fonctionnalités**du gestionnaire de serveur, sélectionnez **fonctionnalités**. Sélectionnez **Windows Identity Foundation 3,5** dans la liste. Cliquez sur **suivant**, puis sur **installer**.

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a>N’installez pas les LSP (Layered Socket Provider) sur les serveurs multimédias

N’installez pas de logiciel client Microsoft Internet Security and Acceleration (ISA) Server, ni aucun autre logiciel de fournisseurs de services en couche (LSP) Winsock, sur un serveur frontal ou un serveur de médiation autonome. L’installation de ce logiciel pourrait entraîner des performances de trafic multimédia médiocres.

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

