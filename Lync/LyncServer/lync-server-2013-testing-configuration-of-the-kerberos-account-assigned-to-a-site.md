---
title: Test de la configuration du compte Kerberos affecté à un site
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af595ff7a345f7309f832d76aaf033675755f8da
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a>Test de la configuration du compte Kerberos affecté à un site dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Planification de la vérification</p></td>
<td><p>Tous les jours</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsKerberosAccountAssignment. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de commande test-CsKerberosAccountAssignment vous permet de vérifier qu’un compte Kerberos est associé à un site donné, que ce compte est configuré correctement et que le compte fonctionne comme prévu. Les comptes Kerberos sont des comptes d’ordinateur qui peuvent servir de principal d’authentification pour tous les ordinateurs d’un site qui exécutent Internet Information Server (IIS). Étant donné que ces comptes utilisent le protocole d’authentification Kerberos, les comptes sont appelés comptes Kerberos et le nouveau processus d’authentification est appelé authentification Web Kerberos. Cela vous permet de gérer tous les serveurs IIS à l’aide d’un seul compte.

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) .

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Par défaut, test-CsKerberosAccountAssignment affiche une très petite sortie à l’écran. Au lieu de cela, les informations renvoyées par l’applet de commande sont écrites dans un fichier HTML. Pour cette raison, nous vous recommandons d’inclure le paramètre Verbose et le paramètre report à chaque fois que vous exécutez la commande test-CsKerberosAccountAssignment. Le paramètre Verbose fournira une sortie plus détaillée à l’écran pendant l’exécution de l’applet de commande. Le paramètre Report vous permet de spécifier un chemin d’accès et un nom de fichier pour le fichier HTML généré par test-CsKerberosAccountAssignment. Si vous n’incluez pas le paramètre Report, le fichier HTML est automatiquement enregistré dans votre dossier Users et reçoit un nom semblable à celui-ci : ce84964a-c4da-4622-ad34-c54ff3ed361f. html.

Vous devez également spécifier une identité de site lors de l’exécution de test-CsKerberosAccountAssignment. Les comptes Kerberos sont attribués au niveau de l’étendue site.

La commande suivante exécute test-CsKerberosAccountAssignment et enregistre la sortie dans un fichier nommé C :\\logs\\KerberosTest. html :

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

L’applet de commande test-CsKerberosAccountAssignment ne renvoie aucune indication simple de réussite ou d’échec. Au lieu de cela, vous devez afficher le fichier HTML généré à l’aide d’Internet Explorer.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques-unes des causes courantes de l’échec de test-CsKerberosAccountAssignment :

  - Vous avez peut-être spécifié une identité de site incorrecte. Pour renvoyer une liste d’identité de site valide, utilisez la commande suivante :
    
        Get-CsSite | Select-Identity Identity
    
    Une identité de site se présente généralement comme suit :
    
    site : Redmond

  - Aucun compte Kerberos n’est affecté au site spécifié. Vous pouvez déterminer si un compte Kerberos est affecté à un site en exécutant une commande semblable à celle-ci :
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - Votre compte Kerberos peut avoir un mot de passe qui n’est pas valide. Si vous recevez le message d’erreur suivant dans le rapport, vous devrez probablement réinitialiser le mot de passe du compte Kerberos :
    
    InvalidKerberosConfiguration : la configuration Kerberos n’est pas valide.
    
    InvalidKerberosConfiguration : la configuration Kerberos sur atl-cs001.litwareinc.com n’est pas valide. Le compte affecté attendu est litwareinc\\kerberostest. Assurez-vous que le compte n’a pas expiré et que le mot de passe configuré sur l’ordinateur correspond au mot de passe Active Directory du compte.
    
    Vous pouvez définir le mot de passe à l’aide de la cmdlet [Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

