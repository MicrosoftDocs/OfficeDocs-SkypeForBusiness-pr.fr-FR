---
title: 'Lync Server 2013 : vérifier les certificats du serveur Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af0a80df18a4fc6e27200d1ac04476fcea798b9b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a>Vérifier les certificats du serveur Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-11-01_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Échéancier de vérification</p></td>
<td><p>Mois</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande Get-CsCertificate. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de passe Get-CsCertificate vous permet de récupérer des informations sur chacun de vos certificats Lync Server. C’est particulièrement important car les certificats disposent d’une date d’expiration prédéfinie. Par exemple, les certificats émis en privé arrivent généralement après 12 mois. Si l’un de vos certificats serveur Lync expire alors, vous perdrez la fonctionnalité qui vous est fournie tant que ce certificat n’est pas renouvelé ou remplacé.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Pour renvoyer des informations sur chacun de vos certificats de serveur Lync, exécutez la commande suivante :

`Get-CsCertificate`

Vous pouvez ou filtrer les informations de certificat de renvoi en fonction de la date d’expiration. Par exemple, la commande suivante permet de limiter les données renvoyées aux certificats qui expirent (ne peut pas être utilisé après le 1er juin), 2014 :

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

Pour plus d’informations, consultez la documentation d’aide relative à l’applet de passe Get-CsCertificate.

Notez que bien que l’applet de contrôle CsCertificateConfiguration de test existe, il n’est pas très utile aux administrateurs. (Au lieu de cela, cette applet de certification est essentiellement utilisée par l’Assistant certificat.) Même si l’applet de commande fonctionne, les informations qu’elle renvoie sont de valeur minimale, comme indiqué dans l’exemple de sortie suivant :

Utilisation de l’empreinte digitale

\---------- ---

A9D51A2911C74FABFF7F2A8A994B20857D399107 par défaut

</div>

<div>

## <a name="reviewing-the-output"></a>Examen de la sortie

L’applet de commande Get-CsCertificate renvoie des informations similaires à ce qui suit pour chacun de vos certificats Lync Server :

Émetteur : CN = FabrikamCA

NotAfter : 12/28/2015 3:35:41 PM

NotBefore : 1/2/2014 12:49:37 PM

SerialNumber : 611BB01200000000000C

Subject : CN = LYNC-SE.fabrikam.com

AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,

meet.fabrikam.com, admin.fabrikam.com...}

Empreinte : A9D51A2911C74FABFF7F2A8A994B20857D399107

Utiliser : par défaut

En règle générale, les principaux problèmes liés aux certificats de serveur Lync concernent les dates et les heures, par exemple lorsque les certificats prennent effet (NotBefore) ou qu’ils arrivent à expiration (NotAfter). Étant donné que ces dates et heures sont si importantes, il est possible que vous souhaitiez limiter les données renvoyées à des informations telles que l’utilisation du certificat, le numéro de série du certificat et la date d’expiration du certificat ; vous pouvez ensuite consulter rapidement tous les certificats et leur date d’expiration. Pour renvoyer uniquement ces informations, utilisez la commande conjointement avec les options proposées :

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

Cette commande renvoie des données similaires à ce qui suit, avec les certificats triés dans l’ordre de leur date d’expiration :

Utiliser SerialNumber NotAfter

\--- ------------ --------

Par défaut 611BB01200000000000C 12/28/2015 3:35:41 PM

WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM

WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM

Si vous rencontrez des problèmes de certificat, vous pouvez consulter le AlternativeNames configuré pour un certificat. Tout d’abord, il semble y avoir un problème. Par défaut, et en fonction de la taille de la fenêtre de la console, Get-CsCertificate peut ne pas être en mesure d’afficher tous les noms :

AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,

meet.fabrikam.com, admin. Fabrika...}

Pour afficher tous les noms de remplacement attribués à un certificat, utilisez une commande similaire à celle-ci :

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

Cela doit afficher tous les noms secondaires sur le certificat :

sip.fabrikam.com

LYNC.fabrikam.com

meet.fabrikam.com

admin.fabrikam.com

LYNC-SE.fabrikam.com

Dialin.fabrikam.com

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Get-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

