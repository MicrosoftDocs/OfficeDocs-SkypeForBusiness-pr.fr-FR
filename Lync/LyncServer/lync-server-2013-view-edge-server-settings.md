---
title: 'Lync Server 2013: afficher les paramètres du serveur de périphérie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 972a5861af803dbaf66843883595c446345ac29a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a>Afficher les paramètres de serveur Edge dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-05-20_

Les configurations de serveur Edge générales doivent être révisées par rapport aux données de la base de données de gestion de la configuration pour garantir que toutes les modifications étaient étayées par les procédures de contrôle de modification définies.

D’autres tests peuvent inclure ceux décrits dans les sections suivantes:

<div>

## <a name="verify-the-allow-and-block-lists"></a>Vérifier les listes d’autorisation et de blocage

Vérifiez les listes d’URI SIP «allow» et «Block» pour les domaines fédérés pour déterminer si les espaces de noms répertoriés sont toujours valides.

Vous pouvez utiliser Windows PowerShell pour afficher les listes autorisées et bloquées. Pour passer en revue les domaines de la liste des domaines autorisés, exécutez la commande Windows PowerShell suivante:

`Get-CsAllowedDomain`

Cette commande renvoie des informations similaires à ce qui suit pour les domaines figurant dans la liste des domaines autorisés:

Identité: contoso.com

Domain: contoso.com

ProxyFqdn :

Comment

MarkForMonitoring: false

Comment

Pour passer en revue les domaines de la liste des domaines bloqués, utilisez la commande suivante:

`Get-CsBlockedDomain`

En retour, vous recevrez des informations telles que celle-ci pour chaque domaine bloqué:

Identité: tailspintoys.com

Domain: tailspintoys.com

Windows PowerShell vous permet également de vérifier que vous pouvez vous connecter aux domaines dans votre liste de domaines autorisés. Par exemple, cette commande vérifie la connexion entre votre serveur Edge (TargetFqdn) et le domaine fédéré contoso.com:

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

Cette commande vérifie la connexion entre votre serveur Edge et tous les domaines qui figurent dans votre liste de domaines autorisés:

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a>Vérifier que plusieurs serveurs Edge sont identiques

Si plusieurs serveurs Edge sont déployés dans un tableau équilibré en charge, nous vous conseillons de vérifier que tous les serveurs Edge du tableau sont configurés de la même manière.

Vous pouvez afficher les paramètres des serveurs de périphérie dans le volet d’informations de l’extension 2013 du serveur Lync pour le composant logiciel enfichable Gestion de l’ordinateur.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Get-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[Get-CsBlockedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

