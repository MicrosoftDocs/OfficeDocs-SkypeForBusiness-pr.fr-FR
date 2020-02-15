---
title: 'Lync Server 2013 : modifier les paramètres de qualité de l’expérience'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify Quality of Experience settings
ms:assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182563(v=OCS.15)
ms:contentKeyID: 48184996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e24d3d0d3b17e5e7b58a6cd58806c3b5ba22e9e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-quality-of-experience-settings-in-lync-server-2013"></a>Modifier les paramètres de qualité de l’expérience dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Par défaut, les données de qualité de l’expérience (QoE) sont vidées au bout de 60 jours. Vous pouvez utiliser les paramètres de la page **Données de qualité de l’expérience** pour conserver les données pendant une période plus longue ou plus courte. Si vous désactivez QoE, les données capturées avant que l’activation de QoE seront également purgées.

<div>


> [!NOTE]  
> Vous devez configurer l’enregistrement des détails des appels (CDR) et QoE pour conserver des données pendant le même nombre de jours. Chaque appel des enregistrements des détails des appels disponible à partir de la page d’accueil des rapports de surveillance inclut des informations sur l’enregistrement des détails des appels et sur la qualité de l’expérience. Si la durée du vidage est différente pour les enregistrements des détails des appels (CDR) et la qualité de l’expérience (QoE), certains appels pourront inclure uniquement des données CDR, tandis que d’autres contiendront uniquement des données QoE.



</div>

La procédure suivante décrit comment configurer des paramètres de vidage pour des données de qualité de l’expérience (QoE).

<div>

## <a name="to-specify-retention-of-qoe-data-by-using-lync-server-control-panel"></a>Pour spécifier la conservation des données QoE à l’aide du panneau de configuration Lync Server

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Données de qualité de l’expérience**.

4.  A la page **Données de qualité de l’expérience**, cliquez sur le site approprié dans le tableau, sur **Modifier**, puis sur **Afficher les détails**.

5.  Pour activer le vidage, sélectionnez **Activer le vidage des données de qualité de l’expérience**.

6.  Dans **Conserver les données QoE pendant la durée maximale (jours)**, sélectionnez le nombre maximal de jours pendant lesquels les données de qualité de l’expérience doivent être conservées.

7.  Cliquez sur **Valider**.

</div>

<div>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>Spécification de la rétention QoE à l’aide des applets de commande Windows PowerShell

Vous pouvez créer des paramètres de rétention QoE à l’aide de Windows PowerShell et de la cmdlet **Set-CsQoEConfiguration** . Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-specify-qoe-retention-for-a-specific-location"></a>Pour spécifier la conservation des données QoE pour un emplacement spécifique

  - Cette commande active le vidage des données QoE pour le site Redmond et configure le site de façon à conserver les données QoE pendant 20 jours.
    
        Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20

</div>

<div>

## <a name="to-specify-qoe-retention-for-multiple-locations"></a>Pour spécifier la conservation des données QoE pour plusieurs emplacements

  - Cette commande configure la conservation des données QoE pour tous les paramètres de configuration QoE utilisés dans une organisation.
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20 

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Déploiement de la surveillance dans Lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

