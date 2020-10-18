---
title: 'Lync Server 2013 : suppression des paramètres de configuration d’un service Web existant'
description: 'Lync Server 2013 : suppression des paramètres de configuration d’un service Web existant.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Web Service configuration settings
ms:assetid: c2b96f4c-4b07-48e6-9ca6-55bc0e0cf5a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182582(v=OCS.15)
ms:contentKeyID: 48185333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a28197f26a447112e29b6e4a831585dd49a9854
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575850"
---
# <a name="delete-existing-web-service-configuration-settings-in-lync-server-2013"></a>Supprimer les paramètres de configuration de service Web existants dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Procédez comme suit pour supprimer les paramètres de configuration du service Web.

<div>

## <a name="to-delete-web-service-configuration-settings"></a>Pour supprimer les paramètres de configuration d’un service Web

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Service web**.

4.  Dans le champ de recherche de la page **Service web**, tapez l’intégralité ou une partie du nom de la stratégie à supprimer.

5.  Dans la liste des stratégies, cliquez sur la stratégie que vous souhaitez supprimer, cliquez sur **Modifier**, puis sur **Supprimer**.

6.  Cliquez sur **OK**.

</div>

<div>

## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Suppression des paramètres de configuration des services Web à l’aide des applets de commande Windows PowerShell

Vous pouvez supprimer les paramètres de configuration des services Web à l’aide de Windows PowerShell et de l’applet de commande **Remove-CsWebServiceConfiguration** . Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>Pour supprimer une collection de paramètres de configuration des services web

  - La commande suivante supprime les paramètres de sécurité des services web appliqués au site de Redmond :
    
        Remove-CsWebServiceConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>Pour supprimer tous les paramètres de configuration de service Web appliqués à l’étendue site

  - La commande suivante supprime tous les paramètres de sécurité des services web appliqués à l’étendue des services :
    
        Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>Pour supprimer tous les paramètres de configuration de service Web qui autorisent l’authentification de certificats

  - La commande suivante supprime tous les paramètres de sécurité des services web qui autorisent l’authentification des certificats :
    
        Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration

</div>

Pour plus d’informations, consultez la rubrique [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration de l’authentification dans le panneau de configuration Lync Server 2013](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

