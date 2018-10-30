---
title: 'Lync Server 2013 : Configuration des services Internet (IIS)'
TOCTitle: Configuration des services Internet (IIS)
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412871(v=OCS.15)
ms:contentKeyID: 49298578
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des services Internet (IIS) dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Pour compléter cette procédure, vous devez être connecté au serveur au minimum en tant qu’administrateur local et en tant qu’utilisateur de domaine.

Avant de configurer et d’installer le serveur frontal pour Lync Server 2013, Standard Edition ou le premier serveur frontal dans un pool, vous installez et configurez le rôle de serveur et les services web pour les services Internet (IIS).

> [!IMPORTANT]  
> Si votre organisation vous oblige à placer les services Internet (IIS) et tous les services web sur un lecteur autre que le lecteur système, vous pouvez modifier le chemin d’accès de l’emplacement d’installation des fichiers Lync Server 2013 dans la boîte de dialogue Installation lors de l’installation initiale des outils d’administration Lync Server 2013. Vous devez installer ces derniers avant d’installer les services Internet (IIS). Si vous installez les fichiers d’installation à cet emplacement, y compris OCSCore.msi, le reste des fichiers Lync Server 2013 est également déployé sur ce même lecteur. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-install-lync-server-administrative-tools.md">Installation des outils d’administration Lync Server 2013</a>. Pour plus d’informations sur la façon de déplacer le composant INETPUB déployé par le Gestionnaire de serveur Windows lors de l’installation des services Internet (IIS), reportez-vous à <a href="http://go.microsoft.com/fwlink/?linkid=216888" class="uri">http://go.microsoft.com/fwlink/?linkid=216888</a>.

Le tableau ci-dessous indique les services de rôle des services Internet (IIS) 7.5 nécessaires.

### Services de rôle des services Internet (IIS) 7.5

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Titre de rôle</th>
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
<p>Windows Server 2012 requiert également ASP.NET 4.5</p></td>
</tr>
<tr class="odd">
<td><p>Développement d’applications</p></td>
<td><p>Extensibilité .NET</p></td>
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
<td><p>Intégrité et diagnostics</p></td>
<td><p>Journalisation HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Intégrité et diagnostics</p></td>
<td><p>Outils de journalisation</p></td>
</tr>
<tr class="even">
<td><p>Intégrité et diagnostics</p></td>
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
<td><p>Authentification par mappage de certificat client</p></td>
</tr>
<tr class="even">
<td><p>Sécurité</p></td>
<td><p>Filtrage des demandes</p></td>
</tr>
<tr class="odd">
<td><p>Performances</p></td>
<td><p>Compression du contenu statique</p>
<p>Compression du contenu dynamique</p></td>
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


Sur le système d’exploitation Windows Server 2008 R2 SP1 x64, vous pouvez utiliser Windows PowerShell 2.0. Vous devez d’abord importer le module ServerManager, puis installer le rôle et les services de rôle des services Internet (IIS) 7.5.

```
Import-Module ServerManager
```
```
Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
```

> [!NOTE]  
> L’authentification anonyme est installée par défaut avec le rôle serveur des services Internet (IIS). Vous pouvez gérer l’authentification anonyme après l’installation des services Internet (IIS). Pour plus d’informations, reportez-vous à « Activer l’authentification anonyme (services Internet [IIS] 7) » à l’adresse <a href="http://go.microsoft.com/fwlink/?linkid=203935" class="uri">http://go.microsoft.com/fwlink/?linkid=203935</a>.

Le tableau ci-dessous indique les services de rôle des services Internet (IIS) 8.0 et des services Internet (IIS) 8.5 nécessaires pour Windows Server 2012 et Windows Server 2012 R2.

> [!NOTE]  
> Pour Windows Server 2012 et Windows Server 2012 R2, l’applet de commande Add-WindowsFeature a été remplacée par Install-WindowsFeature. Pour plus d’informations, reportez-vous à <a href="http://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</a>.

### Services de rôle des services Internet (IIS) 8.0 et des services Internet (IIS) 8.5

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Titre de rôle</th>
<th>Service de rôle</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serveur web (services Internet [IIS])</p></td>
<td><p>Serveur web</p></td>
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
<td><p>Redirection HTTP</p></td>
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
<td><p>Observateur de demandes</p></td>
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
<td><p>Extensibilité .NET 3.5</p></td>
</tr>
<tr class="even">
<td><p>Développement d’applications</p></td>
<td><p>Extensibilité .NET 4.5</p></td>
</tr>
<tr class="odd">
<td><p>Développement d’applications</p></td>
<td><p>ASP.NET 3.5</p></td>
</tr>
<tr class="even">
<td><p>Développement d’applications</p></td>
<td><p>ASP.NET 4.5</p></td>
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
<td><p>Fichiers Include côté serveur</p></td>
</tr>
<tr class="even">
<td><p>Outils de gestion</p></td>
<td><p>Console de gestion des services Internet (IIS)</p></td>
</tr>
<tr class="odd">
<td><p>Outils de gestion</p></td>
<td><p>Compatibilité avec la gestion des services Internet (IIS) 6</p></td>
</tr>
<tr class="even">
<td><p>Outils de gestion</p></td>
<td><p>Scripts et outils de gestion des services Internet (IIS)</p></td>
</tr>
<tr class="odd">
<td><p>Fonctionnalités du .NET 3.5 Framework</p></td>
<td><p>.NET 3.5 Framework</p></td>
</tr>
<tr class="even">
<td><p>Fonctionnalités du .NET 4.5 Framework</p></td>
<td><p>.NET 4.5 Framework</p></td>
</tr>
<tr class="odd">
<td><p>Fonctionnalités du .NET 4.5 Framework</p></td>
<td><p>ASP.NET 4.5</p></td>
</tr>
<tr class="even">
<td><p>Fonctionnalités du .NET 4.5 Framework</p></td>
<td><p>Activation HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Fonctionnalités du .NET 4.5 Framework</p></td>
<td><p>Partage de port TCP</p></td>
</tr>
<tr class="even">
<td><p>Service de transfert intelligent en arrière-plan (BITS)</p></td>
<td><p>Extensions de serveur des services Internet (IIS)</p></td>
</tr>
<tr class="odd">
<td><p>Services de prise en charge de l’écriture manuscrite</p></td>
<td><p>Services de prise en charge de l’écriture manuscrite</p></td>
</tr>
<tr class="even">
<td><p>Media Foundation</p></td>
<td><p>Media Foundation</p></td>
</tr>
<tr class="odd">
<td><p>Interfaces utilisateur et infrastructure</p></td>
<td><p>Outils de gestion graphique et infrastructure</p></td>
</tr>
<tr class="even">
<td><p>Interfaces utilisateur et infrastructure</p></td>
<td><p>Expérience utilisateur</p></td>
</tr>
<tr class="odd">
<td><p>Interfaces utilisateur et infrastructure</p></td>
<td><p>Interpréteur de commandes graphique de serveur</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation 3.5</p></td>
<td><p>Windows Identity Foundation 3.5</p></td>
</tr>
<tr class="odd">
<td><p>Service d’activation des processus Windows</p></td>
<td><p>Modèle de processus</p></td>
</tr>
<tr class="even">
<td><p>Service d’activation des processus Windows</p></td>
<td><p>API de configuration</p></td>
</tr>
</tbody>
</table>


Dans Windows Server 2012 et Windows Server 2012 R2, vous pouvez utiliser Windows PowerShell 3.0 pour installer les éléments requis par les services Internet (IIS). À l’aide du module ServerManager dans Windows PowerShell 3.0, saisissez :

```
Import-Module ServerManager
```
```
Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
```

> [!IMPORTANT]  
> Le paramètre –Source qui définit l’emplacement où se trouve le média source Windows Server 2012 est une nouveauté dans Windows Server 2012. Le média peut être défini en tant que lecteur de DVD (par exemple, D:\Sources\Sxs) ou en tant que partage réseau sur lequel les fichiers multimédias ont été copiés (par exemple, \\fileserver\windows2012\sources\Sxs).

## Voir aussi

#### Concepts

[Configuration requise pour les services Internet (IIS) pour les pools frontaux et les serveurs Standard Edition dans Lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

