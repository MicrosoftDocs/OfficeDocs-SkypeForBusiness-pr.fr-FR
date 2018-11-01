---
title: 'Lync Server 2013 : Configuration de la page de participation à une réunion'
TOCTitle: Configuration de la page de participation à une réunion
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204861(v=OCS.15)
ms:contentKeyID: 49297069
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la page de participation à une réunion dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Quand un utilisateur clique sur un lien de réunion dans une demande de réunion, la page de participation aux réunions détecte si un client Lync 2013 est déjà installé sur l’ordinateur de l’utilisateur. Si c’est le cas, ce client s’ouvre et se joint à la réunion. Dans le cas contraire, la version 2013 de Lync Web App s’ouvre.

Vous pouvez modifier le comportement de la page de participation aux réunions si vous voulez permettre aux utilisateurs de se joindre aux réunions via Office Communicator 2007 R2 ou Intendant Lync 2010. Même si ces options de configuration ont été supprimées du Panneau de configuration Lync Server 2013, vous pouvez toujours les configurer à l’aide de l’applet de commande Set-CsWebServiceConfiguration.

### Paramètres Set-CsWebServiceConfiguration de la page de participation aux réunions

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Paramètre Set-CsWebServiceConfiguration</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>S’il est configuré avec la valeur True, les utilisateurs qui se joignent à une réunion en utilisant une autre application que Lync pourront s’y joindre via Office Communicator 2007 R2. La valeur par défaut est False.</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>Lorsqu’il est défini sur True, les autres options pour rejoindre une conférence en ligne (comme Office Communicator 2007 R2) seront automatiquement développées et montrées aux utilisateurs. Lorsqu’il est défini sur False (valeur par défaut), ces options sont disponibles, mais l’utilisateur doit afficher la liste des options.</p></td>
</tr>
</tbody>
</table>


## Pour configurer la page de participation aux réunions à l’aide de Lync Server 2013 Management Shell

1.  Démarrez Lync Server 2013 Management Shell : cliquez successivement sur **Démarrer** , **Tous les programmes** , **Microsoft Lync Server 2013**, puis **Lync Server Management Shell**.

2.  Pour afficher les paramètres de configuration du service web, exécutez l’applet de commande suivante :
    
        Get-CsWebServiceConfiguration

3.  Exécutez la commande suivante et définissez les paramètres sur True ou False, selon vos préférences (pour plus d’informations sur les paramètres de cette applet de commande, reportez-vous à la documentation [Set-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsWebServiceConfiguration) dans le Lync Server 2013 Management Shell):
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

## Voir aussi

#### Autres ressources

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsWebServiceConfiguration)

