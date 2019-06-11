---
title: Test de la configuration du compte Kerberos affecté à un site
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e12a780c4c900423b23eff6cdaae15ba15786b6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846547"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a>Test de la configuration du compte Kerberos attribué à un site dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Échéancier de vérification</p></td>
<td><p>Jour</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsKerberosAccountAssignment. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de contrôle test-CsKerberosAccountAssignment vous permet de vérifier qu’un compte Kerberos est associé à un site donné, que ce compte est configuré correctement et que le compte fonctionne comme prévu. Les comptes Kerberos sont des comptes d’ordinateur qui peuvent servir d’identité d’authentification pour tous les ordinateurs d’un site exécutant Internet Information Server (IIS). Étant donné que ces comptes utilisent le protocole d’authentification Kerberos, les comptes sont appelés comptes Kerberos et le nouveau processus d’authentification est appelé authentification Web Kerberos. Cela vous permet de gérer tous les serveurs IIS en utilisant un seul compte.

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) .

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Par défaut, test-CsKerberosAccountAssignment affiche un faible niveau de sortie à l’écran. À la place, les informations renvoyées par l’applet de passe sont écrites dans un fichier HTML. Pour cette raison, nous vous recommandons d’inclure le paramètre Verbose et le paramètre de rapport chaque fois que vous exécutez test-CsKerberosAccountAssignment. Le paramètre Verbose fournit un affichage à l’écran détaillé légèrement plus détaillé lors de l’exécution de la cmdlet. Le paramètre rapport vous permet de spécifier un chemin d’accès et un nom de fichier pour le fichier HTML généré par test-CsKerberosAccountAssignment. Si vous n’incluez pas le paramètre de rapport, le fichier HTML sera automatiquement enregistré dans votre dossier utilisateurs et sera doté du nom semblable à ce qui suit: ce84964a-c4da-4622-ad34-c54ff3ed361f. html.

Vous devez également spécifier une identité de site lorsque vous exécutez test-CsKerberosAccountAssignment. Les comptes Kerberos sont attribués au niveau du site.

La commande suivante exécute test-CsKerberosAccountAssignment et enregistre la sortie dans un fichier nommé C:\\logs\\KerberosTest. html:

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

L’applet de contrôle test-CsKerberosAccountAssignment ne renvoie aucune indication simple de réussite ou d’échec. Au lieu de cela, vous devez afficher le fichier HTML généré à l’aide d’Internet Explorer.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles les tests-CsKerberosAccountAssignment peuvent échouer:

  - Vous avez peut-être spécifié une identité de site incorrecte. Pour renvoyer une liste d’identité de site valide, utilisez la commande suivante:
    
        Get-CsSite | Select-Identity Identity
    
    En règle générale, l’identité d’un site ressemble à ceci:
    
    site: Redmond

  - Il est possible qu’aucun compte Kerberos ne soit affecté au site indiqué. Vous pouvez déterminer si un compte Kerberos est ou non affecté à un site en exécutant une commande semblable à ce qui suit:
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - Il est possible que votre compte Kerberos comporte un mot de passe qui n’est pas valide. Si vous recevez le message d’erreur suivant dans le rapport, vous devrez probablement réinitialiser le mot de passe du compte Kerberos:
    
    InvalidKerberosConfiguration: la configuration Kerberos n’est pas valide.
    
    InvalidKerberosConfiguration: la configuration Kerberos sur atl-cs001.litwareinc.com n’est pas valide. Le compte affecté attendu est litwareinc\\kerberostest. Vérifiez que le compte n’a pas expiré et que le mot de passe configuré sur l’ordinateur correspond au mot de passe Active Directory du compte.
    
    Vous pouvez définir le mot de passe à l’aide de l’applet de passe [Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

