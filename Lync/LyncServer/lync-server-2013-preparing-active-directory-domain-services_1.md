---
title: 'Lync Server 2013 : préparation des services de domaine Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b3af3ce7940b8d0fb58a74b4a8f7bb0a21c5e2d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506991"
---
# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a>Préparation des services de domaine Active Directory dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-19_

Dans Lync Server 2013, vous pouvez utiliser l’Assistant Déploiement Lync Server pour préparer les services de domaine Active Directory ou vous pouvez utiliser les applets de commande Lync Server Management Shell directement. Vous pouvez également utiliser la ligne de commande directement sur vos contrôleurs de domaine, comme expliqué plus loin dans cette rubrique.

L’Assistant Déploiement de Lync Server vous guide à travers chaque tâche de préparation d’Active Directory. L’Assistant Déploiement exécute des applets de commande Lync Server Management Shell. Cet outil est utile pour les environnements avec une topologie à un seul domaine et à une seule forêt ou avec une autre topologie semblable.

<div>


> [!IMPORTANT]  
> Vous pouvez déployer Lync Server dans une forêt ou un domaine où des contrôleurs de domaine exécutent des versions 32 bits de certains systèmes d’exploitation (pour plus d’informations, consultez la rubrique <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory infrastructure Requirements for Lync Server 2013</A>). Toutefois, vous ne pouvez pas utiliser l’Assistant Déploiement Lync Server pour exécuter la préparation des schémas, des forêts et des domaines dans ces environnements, car l’Assistant Déploiement et les fichiers de prise en charge sont 64 bits uniquement. À la place, vous pouvez utiliser ldifde.exe et les fichiers .ldf associés sur un contrôleur de domaine 32 bits pour préparer le schéma, la forêt et le domaine. Voir la section « Utilisation des applets de commande et de Ldifde.exe » dans cette rubrique.



</div>

Vous pouvez utiliser des applets de commande Lync Server Management Shell pour exécuter des tâches à distance ou pour des environnements plus complexes.

<div>

## <a name="active-directory-preparation-prerequisites"></a>Conditions préalables à la préparation d’Active Directory

Vous devez exécuter les étapes de préparation d’Active Directory sur un ordinateur exécutant Windows Server 2012, Windows Server 2012 R2 ou Windows Server 2008 R2 avec SP1 (64 bits). La préparation d’Active Directory requiert Lync Server Management Shell et OCSCore.

Les composants suivants sont requis pour exécuter les tâches de préparation d’Active Directory :

  - Composants principaux de Lync Server (OCScore.msi)
    
    <div>
    

    > [!NOTE]  
    > Si vous envisagez d’utiliser Lync Server Management Shell pour la préparation d’Active Directory, vous devez d’abord exécuter l’Assistant Déploiement de Lync Server pour installer les composants principaux.

    
    </div>

  - Microsoft .NET Framework 4.5
    
    <div>
    

    > [!NOTE]  
    > Pour Windows Server 2012 et Windows Server 2012 R2, vous devez installer et activer .NET Framework 4,5 à l’aide du gestionnaire de serveur. Pour plus d’informations, voir « Microsoft .NET Framework 4,5 » dans la rubrique relative <A href="lync-server-2013-additional-software-requirements.md">à la configuration logicielle requise pour Lync Server 2013</A>. Pour Windows Server &nbsp; 2008 &nbsp; R2, téléchargez et installez <A href="https://www.microsoft.com/download/details.aspx?id=30653">.NET Framework 4,5</A> à partir du site Web de Microsoft.

    
    </div>

  - Outils d’administration de serveur distant (RSAT)
    
    <div>
    

    > [!NOTE]  
    > Certains outils RSAT sont nécessaires si vous exécutez les étapes de préparation d’Active Directory sur un serveur membre plutôt que sur un contrôleur de domaine. Installez les composants logiciels enfichables AD DS et les outils en ligne de commande et le module Active Directory pour Windows PowerShell à partir du nœud AD DS et AD LDS Tools dans le gestionnaire de serveur.

    
    </div>

  - Microsoft Visual C++ 11 Redistributable
    
    <div>
    

    > [!NOTE]  
    > Le programme d’installation vous invite à l’installer s’il n’est pas déjà sur l’ordinateur. Le package vous est fourni, il est inutile de l’acquérir séparément.

    
    </div>

  - Windows PowerShell 3,0 (64 bits)
    
    Pour Windows Server 2012 et Windows Server 2012 R2, Windows PowerShell 3,0 doit être inclus dans votre installation Lync Server 2013. Pour Windows Server 2008 R2, vous devez installer ou effectuer une mise à niveau vers Windows PowerShell 3,0. Pour plus d’informations, consultez la rubrique [installation de Windows PowerShell 3,0 pour Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)

</div>

<div>

## <a name="administrator-rights-and-roles"></a>Droits et rôles d’administrateur

Le tableau ci-après répertorie les droits et rôles d’administration requis pour chaque tâche de préparation d’Active Directory.

### <a name="user-rights-required-for-active-directory-preparation"></a>Droits de l’utilisateur requis pour la préparation d’Active Directory

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Procédure</th>
<th>Droits ou rôles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Préparation d’un schéma</p></td>
<td><p>Membre du groupe Administrateurs du schéma pour le domaine racine de la forêt et droits d’administrateur sur le contrôleur de schéma</p></td>
</tr>
<tr class="even">
<td><p>Préparation d’une forêt</p></td>
<td><p>Membre du groupe Administrateurs de l’entreprise pour la forêt</p></td>
</tr>
<tr class="odd">
<td><p>Préparation d’un domaine</p></td>
<td><p>Membre du groupe Administrateurs de l’entreprise ou Administrateurs du domaine pour le domaine spécifié</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a>Applets de commande de préparation d’Active Directory

Le tableau suivant compare les applets de commande Lync Server Management Shell utilisées pour préparer AD DS aux commandes LcsCmd utilisées pour préparer AD DS dans Microsoft Office Communications Server 2007 R2.

### <a name="cmdlets-compared-to-lcscmd"></a>Applets de commande par rapport à LcsCmd

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Cmdlets</th>
<th>LcsCmd</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Install-CsAdServerSchema</p></td>
<td><p>Lcscmd /forest /action:SchemaPrep /SchemaType:Server</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdServerSchema</p></td>
<td><p>Lcscmd /forest /action:CheckSchemaPrepState</p></td>
</tr>
<tr class="odd">
<td><p>Enable-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:ForestPrep</p></td>
</tr>
<tr class="even">
<td><p>Disable-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:ForestUnprep</p></td>
</tr>
<tr class="odd">
<td><p>Get-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:CheckForestPrepState</p></td>
</tr>
<tr class="even">
<td><p>Enable-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action:DomainPrep</p></td>
</tr>
<tr class="odd">
<td><p>Disable-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action: DomainUnprep</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action:CheckDomainPrepState</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a>Configuration requise pour des services de domaine Active Directory verrouillés

Si l’héritage des autorisations est désactivé ou que les autorisations des utilisateurs authentifiés doivent être désactivées dans votre organisation, vous devez exécuter des étapes supplémentaires dans le cadre de la procédure de préparation d’un domaine. Pour plus d’informations, reportez-vous à la rubrique [préparation d’un service de domaine Active Directory verrouillé dans Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

</div>

<div>

## <a name="custom-container-permissions"></a>Autorisations de conteneur personnalisé

Si votre organisation utilise des conteneurs personnalisés à la place des trois conteneurs intégrés (Utilisateurs, Ordinateurs et Contrôleurs de domaine), vous devez octroyer au groupe Utilisateurs authentifiés un accès en lecture aux conteneurs personnalisés. L’accès en lecture aux conteneurs est obligatoire pour la préparation du domaine. Pour plus d’informations, consultez la rubrique [Preparing Domains for Lync Server 2013](lync-server-2013-preparing-domains.md).

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a>Utilisation des applets de commande et de Ldifde.exe

L’étape **préparer le schéma** de l’Assistant Déploiement de Lync Server et de l’applet de commande **install-CsAdServerSchema** étend le schéma Active Directory sur les contrôleurs de domaine exécutant un système d’exploitation 64 bits. Si vous devez étendre le schéma Active Directory sur un contrôleur de domaine qui exécute un système d’exploitation 32 bits, vous pouvez exécuter l’applet de commande **Install-CsAdServerSchema** à distance depuis un serveur membre (approche recommandée). Si toutefois vous devez exécuter la préparation du schéma directement sur le contrôleur de domaine, vous pouvez utiliser l’outil Ldifde.exe pour importer les fichiers de schéma. L’outil Ldifde.exe est livré avec la plupart des versions du système d’exploitation Windows.

Si vous utilisez Ldife.exe pour importer les fichiers de schéma, vous devez importer les quatre fichiers, même si vous procédez à une migration depuis une version précédente ou à une nouvelle installation. Vous devez les importer dans l’ordre suivant :

1.  ExternalSchema. ldf

2.  ServerSchema. ldf

3.  BackCompatSchema. ldf

4.  VersionSchema. ldf

<div>


> [!NOTE]  
> Les quatre fichiers .ldf se trouvent dans le répertoire \Support\Schema de votre support d’installation ou de téléchargement.



</div>

Pour utiliser Ldifde.exe pour importer les quatre fichiers de schéma sur un contrôleur de domaine qui est également le contrôleur de schéma, utilisez le format suivant :

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

Par exemple :

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> Utilisez le paramètre b seulement si vous êtes connecté en tant qu’un autre utilisateur. Pour plus d’informations sur les droits d’utilisateur requis, voir la section « Droits et rôles d’administrateur » abordée précédemment dans cette rubrique.



</div>

Pour utiliser Ldifde.exe pour importer les quatre fichiers de schéma sur un contrôleur de domaine qui n’est pas le contrôleur de schéma, utilisez le format suivant :

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

Pour plus d’informations sur l’utilisation de LDIFDE, consultez l’article 237677 de la base de connaissances Microsoft, « utilisation de LDIFDE pour importer et exporter des objets d’annuaire dans Active Directory », à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=132204](https://go.microsoft.com/fwlink/p/?linkid=132204) .

</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Préparation du schéma Active Directory dans Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)

  - [Préparation de la forêt pour Lync Server 2013](lync-server-2013-preparing-the-forest.md)

  - [Préparation des domaines pour Lync Server 2013](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

