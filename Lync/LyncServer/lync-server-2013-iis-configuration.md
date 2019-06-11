---
title: 'Lync Server 2013 : Configuration des services Internet (IIS)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de2205ad049beb05f30dd58795257b62eca68d46
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-configuration-in-lync-server-2013"></a>Configuration des services Internet (IIS) dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-02-17_

Pour effectuer cette procédure, vous devez être connecté au serveur au minimum en tant qu’administrateur local et utilisateur de domaine.

Avant de configurer et d’installer le serveur frontal pour Lync Server 2013, Standard Edition ou le premier serveur frontal d’un pool, vous installez et configurez le rôle de serveur et les services Web pour Internet Information Services (IIS).

<div class=" ">


> [!IMPORTANT]  
> Si votre organisation nécessite que vous localisiez IIS et tous les services Web sur un lecteur autre que le lecteur système, vous pouvez modifier le chemin d’accès d’installation pour les fichiers Lync Server 2013 dans la boîte de dialogue de configuration lors de l’installation initiale de Lync Server 2013 Outils d’administration. Vous installez les outils d’administration avant d’installer IIS. Si vous installez les fichiers d’installation dans ce chemin d’accès, y compris OCSCore. msi, les autres fichiers Lync Server 2013 sont déployés également sur ce lecteur. Pour dtails, voir <A href="lync-server-2013-install-lync-server-administrative-tools.md">installer les outils d’administration de Lync Server 2013</A>. Pour plus d’informations sur la façon de déplacer le INETPUB déployé par Windows Server Manager lors de l' <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>installation d’IIS, voir.



</div>

Le tableau suivant indique les services de rôles IIS 7,5 requis.

### <a name="iis-75-role-services"></a>Services de rôle 7,5 IIS

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Titre du rôle</th>
<th>Service de rôle</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Fonctionnalités HTTP communes installées</p></td>
<td><p>Contenu statique</p></td>
</tr>
<tr class="even">
<td><p>Fonctionnalités HTTP communes installées</p></td>
<td><p>Document par défaut</p></td>
</tr>
<tr class="odd">
<td><p>Fonctionnalités HTTP communes installées</p></td>
<td><p>Erreurs HTTP</p></td>
</tr>
<tr class="even">
<td><p>Développement d’applications</p></td>
<td><p>ASP.NET</p>
<p>Windows Server 2012 nécessite également ASP. NET 4.5</p></td>
</tr>
<tr class="odd">
<td><p>Développement d’applications</p></td>
<td><p>Extensibilité .NET</p></td>
</tr>
<tr class="even">
<td><p>Développement d’applications</p></td>
<td><p>Extensions ISAPI (Internet Server API)</p></td>
</tr>
<tr class="odd">
<td><p>Développement d’applications</p></td>
<td><p>Filtres ISAPI</p></td>
</tr>
<tr class="even">
<td><p>État d’intégrité et diagnostics</p></td>
<td><p>Journalisation HTTP</p></td>
</tr>
<tr class="odd">
<td><p>État d’intégrité et diagnostics</p></td>
<td><p>Outils de journalisation</p></td>
</tr>
<tr class="even">
<td><p>État d’intégrité et diagnostics</p></td>
<td><p>Suivi</p></td>
</tr>
<tr class="odd">
<td><p>Sécurité</p></td>
<td><p>Authentification anonyme (installée et activée par défaut)</p></td>
</tr>
<tr class="even">
<td><p>Sécurité</p></td>
<td><p>Authentification Windows</p></td>
</tr>
<tr class="odd">
<td><p>Sécurité</p></td>
<td><p>Authentification du mappage de certificat client</p></td>
</tr>
<tr class="even">
<td><p>Sécurité</p></td>
<td><p>Filtrage de requête</p></td>
</tr>
<tr class="odd">
<td><p>Performances</p></td>
<td><p>Compression de contenu statique</p>
<p>Compression de contenu dynamique</p></td>
</tr>
<tr class="even">
<td><p>Outils de gestion</p></td>
<td><p>Console de gestion des services Internet (IIS)</p></td>
</tr>
<tr class="odd">
<td><p>Outils de gestion</p></td>
<td><p>Scripts et outils de gestion des services Internet (IIS)</p></td>
</tr>
</tbody>
</table>


Sur le système d’exploitation Windows Server 2008 R2 SP1 x64, vous pouvez utiliser Windows PowerShell 2,0. Vous devez d’abord importer le module ServerManager, puis installer les services de rôles et de rôles IIS 7,5.

   ```
    Import-Module ServerManager
   ```

   ```
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> L’authentification anonyme est installée par défaut avec le rôle serveur IIS. Vous pouvez gérer l’authentification anonyme après l’installation d’IIS. Pour en savoir plus, voir Activer l’authentification anonyme (IIS 7) <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>.



</div>

Le tableau suivant indique les services de rôles IIS 8,0 et IIS 8,5 requis pour Windows Server 2012 et Windows Server 2012 R2.

<div class=" ">


> [!NOTE]  
> Pour Windows Server 2012 et Windows Server 2012 R2, l’applet de la cmdlet Add-WindowsFeature a été remplacée par l’applet de passe install-WindowsFeature. Pour plus d’informations, consultez la rubrique <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">installer-WindowsFeature</A>.



</div>

### <a name="iis-80-and-iis-85-role-services"></a>Services de rôle IIS 8,0 et IIS 8,5

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Titre du rôle</th>
<th>Service de rôle</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serveur Web (IIS)</p></td>
<td><p>Serveur Web</p></td>
</tr>
<tr class="even">
<td><p>Fonctionnalités HTTP communes</p></td>
<td><p>Document par défaut</p></td>
</tr>
<tr class="odd">
<td><p>Fonctionnalités HTTP communes</p></td>
<td><p>Exploration des répertoires</p></td>
</tr>
<tr class="even">
<td><p>Fonctionnalités HTTP communes</p></td>
<td><p>Erreurs HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Fonctionnalités HTTP communes</p></td>
<td><p>Contenu statique</p></td>
</tr>
<tr class="even">
<td><p>Fonctionnalités HTTP communes</p></td>
<td><p>Redirection HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Intégrité et diagnostics</p></td>
<td><p>Journalisation HTTP</p></td>
</tr>
<tr class="even">
<td><p>Intégrité et diagnostics</p></td>
<td><p>Outils de journalisation</p></td>
</tr>
<tr class="odd">
<td><p>Intégrité et diagnostics</p></td>
<td><p>Moniteur de requête</p></td>
</tr>
<tr class="even">
<td><p>Intégrité et diagnostics</p></td>
<td><p>Suivi</p></td>
</tr>
<tr class="odd">
<td><p>Sécurité</p></td>
<td><p>Filtrage des demandes</p></td>
</tr>
<tr class="even">
<td><p>Sécurité</p></td>
<td><p>Authentification de base</p></td>
</tr>
<tr class="odd">
<td><p>Sécurité</p></td>
<td><p>Authentification par mappage de certificat client</p></td>
</tr>
<tr class="even">
<td><p>Sécurité</p></td>
<td><p>Authentification Windows</p></td>
</tr>
<tr class="odd">
<td><p>Développement d’applications</p></td>
<td><p>Extensibilité .net 3,5</p></td>
</tr>
<tr class="even">
<td><p>Développement d’applications</p></td>
<td><p>Extensibilité .net 4,5</p></td>
</tr>
<tr class="odd">
<td><p>Développement d’applications</p></td>
<td><p>ASP.Net 3,5</p></td>
</tr>
<tr class="even">
<td><p>Développement d’applications</p></td>
<td><p>ASP.Net 4,5</p></td>
</tr>
<tr class="odd">
<td><p>Développement d’applications</p></td>
<td><p>Extensions ISAPI</p></td>
</tr>
<tr class="even">
<td><p>Développement d’applications</p></td>
<td><p>Filtres ISAPI</p></td>
</tr>
<tr class="odd">
<td><p>Développement d’applications</p></td>
<td><p>Inclusions côté serveur</p></td>
</tr>
<tr class="even">
<td><p>Outils de gestion</p></td>
<td><p>Console de gestion des services Internet (IIS)</p></td>
</tr>
<tr class="odd">
<td><p>Outils de gestion</p></td>
<td><p>Compatibilité de la métabase IIS 6</p></td>
</tr>
<tr class="even">
<td><p>Outils de gestion</p></td>
<td><p>Scripts et outils de gestion des services Internet (IIS)</p></td>
</tr>
<tr class="odd">
<td><p>Fonctionnalités d’infrastructure .net 3,5</p></td>
<td><p>.Net 3,5 Framework</p></td>
</tr>
<tr class="even">
<td><p>Fonctionnalités d’infrastructure .net 4,5</p></td>
<td><p>.NET Framework 4,5</p></td>
</tr>
<tr class="odd">
<td><p>Fonctionnalités d’infrastructure .net 4,5</p></td>
<td><p>ASP.Net 4,5</p></td>
</tr>
<tr class="even">
<td><p>Fonctionnalités d’infrastructure .net 4,5</p></td>
<td><p>Activation HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Fonctionnalités d’infrastructure .net 4,5</p></td>
<td><p>Partage de port TCP</p></td>
</tr>
<tr class="even">
<td><p>Service de transfert intelligent en arrière-plan</p></td>
<td><p>Extensions serveur IIS</p></td>
</tr>
<tr class="odd">
<td><p>Services d’entrée manuscrite</p></td>
<td><p>Services d’entrée manuscrite</p></td>
</tr>
<tr class="even">
<td><p>Media Foundation</p></td>
<td><p>Media Foundation</p></td>
</tr>
<tr class="odd">
<td><p>Interfaces utilisateur et infrastructure</p></td>
<td><p>Outils et infrastructure de gestion graphique</p></td>
</tr>
<tr class="even">
<td><p>Interfaces utilisateur et infrastructure</p></td>
<td><p>Expérience de bureau</p></td>
</tr>
<tr class="odd">
<td><p>Interfaces utilisateur et infrastructure</p></td>
<td><p>Shell graphique serveur</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation 3.5</p></td>
<td><p>Windows Identity Foundation 3.5</p></td>
</tr>
<tr class="odd">
<td><p>Service d’activation de processus Windows</p></td>
<td><p>Modèle de processus</p></td>
</tr>
<tr class="even">
<td><p>Service d’activation de processus Windows</p></td>
<td><p>API de configuration</p></td>
</tr>
</tbody>
</table>


Dans Windows Server 2012 et Windows Server 2012 R2, vous pouvez utiliser Windows PowerShell 3,0 pour installer la configuration requise pour les services Internet (IIS). À l’aide du module ServerManager dans Windows PowerShell 3,0, tapez:

   ```
    Import-Module ServerManager
   ```

   ```
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> Une nouveauté de Windows Server 2012 est le paramètre – source qui définit l’emplacement où se trouve le média source de Windows Server 2012. Le média peut être défini comme lecteur DVD (par exemple, D:\Sources\Sxs) ou sur un partage réseau pour lequel les fichiers multimédias ont été copiés (par exemple \\, fileserver\windows2012\sources\Sxs).



</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration requise pour les services Internet (IIS) pour les pools frontaux et les serveurs Standard Edition dans Lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

