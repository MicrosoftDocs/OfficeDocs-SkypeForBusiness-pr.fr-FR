---
title: 'Lync Server 2013: modifier les paramètres de qualité de l’expertise'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify Quality of Experience settings
ms:assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182563(v=OCS.15)
ms:contentKeyID: 48184996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ce6041e6512714f10785cf2976727788e105f70
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-quality-of-experience-settings-in-lync-server-2013"></a>Modifier les paramètres de qualité d’expérimentation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-23_

Par défaut, les données de qualité de l’expérience (QoE) sont vidées au bout de 60 jours. Vous pouvez utiliser les paramètres de la page **Données de qualité de l’expérience** pour conserver les données pendant une période plus longue ou plus courte. Si vous désactivez QoE, les données capturées avant que l’activation de QoE seront également purgées.

<div>


> [!NOTE]  
> Vous devez configurer l’enregistrement des détails des appels (CDR) et QoE pour conserver des données pendant le même nombre de jours. Chaque appel des enregistrements des détails des appels disponible à partir de la page d’accueil des rapports de surveillance inclut des informations sur l’enregistrement des détails des appels et sur la qualité de l’expérience. Si la durée du vidage est différente pour les enregistrements des détails des appels (CDR) et la qualité de l’expérience (QoE), certains appels pourront inclure uniquement des données CDR, tandis que d’autres contiendront uniquement des données QoE.



</div>

La procédure suivante décrit comment configurer des paramètres de vidage pour des données de qualité de l’expérience (QoE).

<div>

## <a name="to-specify-retention-of-qoe-data-by-using-lync-server-control-panel"></a>Pour spécifier la conservation des données QoE en utilisant le panneau de configuration de Lync Server

1.  Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Données de qualité de l’expérience**.

4.  Dans la page **Données de qualité de l’expérience**, cliquez sur le site approprié dans le tableau, sur **Modifier**, puis sur **Afficher les détails**.

5.  Pour activer le vidage, sélectionnez **Activer le vidage des données de qualité de l’expérience**.

6.  Dans **Conserver les données QoE pendant la durée maximale (jours)**, sélectionnez le nombre maximal de jours pendant lesquels les données de qualité de l’expérience doivent être conservées.

7.  Cliquez sur **Valider**.

</div>

<div>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>Spécification de la rétention QoE en utilisant des applets de cmdlet Windows PowerShell

Vous pouvez créer des paramètres de rétention QoE à l’aide de Windows PowerShell et de l’applet **de cmdlet Set-CsQoEConfiguration** . Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

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

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) .

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

