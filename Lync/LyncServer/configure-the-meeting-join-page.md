---
title: Configuration de la page de participation à la réunion
TOCTitle: Configuration de la page de participation à la réunion
ms:assetid: 036c9d03-ad95-4d63-a3d8-6cae1a8ad530
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204635(v=OCS.15)
ms:contentKeyID: 49296091
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la page de participation à la réunion

 

_**Dernière rubrique modifiée :** 2015-03-09_

Lorsqu’un utilisateur clique sur un lien de réunion dans une demande de réunion, la page de participation à une réunion détermine si un client Lync 2013 est déjà installé sur l‘ordinateur de l’utilisateur. Si tel est le cas, ce client s’ouvre et rejoint la réunion. Si aucun client n’est installé, la version 2013 de Lync Web App s’ouvre par défaut.

Vous pouvez modifier le comportement de la page de participation aux réunions si vous voulez permettre aux utilisateurs de prendre part à des réunions à l’aide d’Office Communicator 2007 R2 ou de Intendant Lync 2010. Même si ces options de configuration ont été supprimées du Panneau de configuration Lync Server 2013, vous pouvez toujours les configurer à l’aide de l’applet de commande CsWebServiceConfiguration.

### Paramètres CsWebServiceConfiguration de la page de participation aux réunions

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Paramètre CsWebServiceConfiguration</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>S’il est configuré avec la valeur True, les utilisateurs qui rejoignent à une réunion en utilisant une application autre que Lync pourront la rejoindre à l’aide d’Office Communicator 2007 R2. La valeur par défaut est False.</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>Lorsqu’il est défini sur True, les autres options pour rejoindre une conférence en ligne (comme Office Communicator 2007 R2) seront automatiquement développées et montrées aux utilisateurs. Lorsqu’il est défini sur False (valeur par défaut), ces options sont disponibles, mais l’utilisateur doit afficher la liste des options.</p></td>
</tr>
</tbody>
</table>


## Pour configurer la page de participation aux réunions à l’aide de Lync Server 2013 Management Shell

1.  Démarrez Lync Server 2013 Management Shell : cliquez successivement sur **Démarrer** , **Tous les programmes** , **Microsoft Lync Server 2013**, puis **Lync Server Management Shell**.

2.  Exécutez l’applet de commande suivante :
    
        Get-CsWebServiceConfiguration
    
    Cette applet de commande renvoie les paramètres de configuration du service web.

3.  Exécutez la commande suivante et définissez les paramètres sur True ou False, selon vos préférences (pour plus d’informations sur les paramètres de cette commande d’applet, reportez-vous à la documentation Lync Server 2013 Management Shell) :
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

