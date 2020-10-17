---
title: 'Lync Server 2013 : afficher les paramètres du serveur Edge'
description: 'Lync Server 2013 : afficher les paramètres du serveur Edge.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4318b8c97f53f267bb79953af504977f6437214d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569680"
---
# <a name="view-edge-server-settings-in-lync-server-2013"></a>Afficher les paramètres du serveur Edge dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-20_

Les configurations de serveur Edge général doivent être comparées aux données de la base de données de gestion de la configuration pour garantir que toutes les modifications ont été documentées conformément aux procédures de contrôle des modifications définies.

Les vérifications supplémentaires peuvent inclure celles qui sont décrites dans les sections suivantes :

<div>

## <a name="verify-the-allow-and-block-lists"></a>Vérifier les listes verte et rouge

Vérifiez les listes d’URI SIP « autoriser » et « bloquer » pour les domaines fédérés afin de déterminer si les espaces de noms répertoriés sont toujours valides.

Vous pouvez utiliser Windows PowerShell pour afficher les listes autorisées et bloquées. Pour passer en revue les domaines de la liste des domaines autorisés, exécutez la commande Windows PowerShell suivante :

`Get-CsAllowedDomain`

Cette commande renvoie des informations semblables à celles-ci pour les domaines de la liste des domaines autorisés :

Identity : contoso.com

Domaine : contoso.com

ProxyFqdn

Commentaire

MarkForMonitoring : false

Commentaire

Pour passer en revue les domaines de la liste des domaines bloqués, utilisez la commande suivante :

`Get-CsBlockedDomain`

En retour, vous recevrez des informations comme celles-ci pour chaque domaine bloqué :

Identity : tailspintoys.com

Domaine : tailspintoys.com

Windows PowerShell vous permet également de vérifier que vous pouvez vous connecter aux domaines de votre liste de domaines autorisés. Par exemple, cette commande vérifie la connexion entre votre serveur Edge (TargetFqdn) et le domaine fédéré contoso.com :

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

Cette commande vérifie la connexion entre votre serveur Edge et tous les domaines figurant dans la liste des domaines autorisés :

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a>Vérifier que plusieurs serveurs Edge sont identiques

Si plusieurs serveurs Edge sont déployés dans un tableau à charge équilibrée, nous vous recommandons de vérifier que tous les serveurs Edge du groupe sont configurés de la même manière.

Vous pouvez afficher les paramètres des serveurs Edge dans le volet d’informations de l’extension Lync Server 2013 pour le composant logiciel enfichable Gestion de l’ordinateur.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Get-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[Get-applet csblockeddomain](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

