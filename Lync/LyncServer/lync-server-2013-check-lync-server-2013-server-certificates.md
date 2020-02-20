---
title: 'Lync Server 2013 : Vérifiez les certificats de serveur Lync Server 2013'
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
ms.openlocfilehash: 2b874c83adb2a1ddb511d8c6980cb12f01e0ef68
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151084"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a>Vérifier les certificats de serveur Lync Server 2013

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
<td><p>Planification de la vérification</p></td>
<td><p>Tous les mois</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Get-CsCertificate. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

La cmdlet Get-CsCertificate vous permet d’extraire des informations sur chacun de vos certificats Lync Server. Cela est particulièrement important, car les certificats ont une date d’expiration intégrée. Par exemple, les certificats émis en privé expirent généralement après 12 mois. Si l’un de vos certificats Lync Server arrive à expiration, vous perdrez les fonctionnalités associées jusqu’à ce que ce certificat soit renouvelé ou remplacé.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Pour renvoyer des informations sur chacun de vos certificats Lync Server, exécutez la commande suivante :

`Get-CsCertificate`

Ou, vous pouvez filtrer les informations de certificat de retour en fonction de la date d’expiration. Par exemple, cette commande limite les données renvoyées aux certificats qui expirent (qui ne peuvent pas être utilisés après) le 1er juin 2014 :

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande Get-CsCertificate.

Notez que, bien que la cmdlet Test-CsCertificateConfiguration existe, elle n’est pas très utile pour les administrateurs. (À la place, cette applet de commande est principalement utilisée par l’Assistant certificat.) Bien que l’applet de commande fonctionne, les informations qu’elle renvoie sont de valeur minimale, comme illustré dans l’exemple de sortie suivant :

Utilisation de l’empreinte numérique

\---------- ---

A9D51A2911C74FABFF7F2A8A994B20857D399107 par défaut

</div>

<div>

## <a name="reviewing-the-output"></a>Révision de la sortie

L’applet de commande Get-CsCertificate renvoie des informations semblables aux suivantes pour chacun de vos certificats Lync Server :

Émetteur : CN = FabrikamCA

NotAfter : 12/28/2015 3:35:41 PM

NotBefore : 1/2/2014 12:49:37 PM

SerialNumber : 611BB01200000000000C

Objet : CN = LYNC-SE.fabrikam.com

AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,

meet.fabrikam.com, admin.fabrikam.com...}

Empreinte numérique : A9D51A2911C74FABFF7F2A8A994B20857D399107

Utiliser : par défaut

En règle générale, les principaux problèmes liés aux certificats Lync Server concernent des dates et des heures, par exemple lorsque des certificats prennent effet (NotBefore) ou lorsqu’ils arrivent à expiration (NotAfter). Étant donné que ces dates et heures sont tellement importantes, vous souhaiterez peut-être limiter les données renvoyées à des informations telles que l’utilisation du certificat, le numéro de série du certificat et la date d’expiration du certificat ; vous pouvez ensuite passer rapidement en revue tous les certificats et leur date d’expiration. Pour renvoyer uniquement ces informations, utilisez la commande avec les options indiquées :

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

Cette commande renvoie des données semblables aux suivantes, dont les certificats sont triés dans l’ordre de leur date d’expiration :

Utiliser le SerialNumber NotAfter

\--- ------------ --------

Valeur par défaut 611BB01200000000000C 12/28/2015 3:35:41 PM

WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM

WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM

Si vous avez des problèmes de certificat, vous pouvez consulter la AlternativeNames configurée pour un certificat. À première vue, il semblerait qu’il s’agit d’un problème. Par défaut, en fonction de la taille de votre fenêtre de console, Get-CsCertificate peut ne pas être en mesure d’afficher tous les noms :

AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,

meet.fabrikam.com, admin. Fabrika...}

Pour afficher tous les autres noms attribués à un certificat, utilisez une commande semblable à celle-ci :

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

Cela doit vous indiquer tous les autres noms du certificat :

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

