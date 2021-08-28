---
title: DNS requirements for simple URLs in Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 'Résumé : Examinez les considérations sur les URL simples dans cette rubrique avant d’implémenter des enregistrements DNS pour Skype Entreprise Server.'
ms.openlocfilehash: a36805566b7bdb9f95ef14b572a8efdccdeb916b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622136"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a>DNS requirements for simple URLs in Skype Entreprise Server

**Résumé :** Examinez les considérations sur les URL simples de cette rubrique avant d’implémenter des enregistrements DNS pour Skype Entreprise Server.

Les URL simples facilitent la réunion pour vos utilisateurs et facilitent l’accès Skype Entreprise Server outils d’administration aux administrateurs. Les URL simples utilisent leur propre domaine, qui ne doit correspondre à aucun des domaines SIP que vous définissez. 

Skype Entreprise Server prend en charge les trois URL simples suivantes : Meet, Dial-In et Admin. Vous devez configurer des URL simples pour Meet et Dial-In, et l’URL simple Admin est facultative. Les enregistrements DNS (Domain Name System) dont vous avez besoin pour prendre en charge les URL simples dépendent de la façon dont vous avez défini ces URL simples et de la prise en charge de la récupération d’urgence pour les URL simples. 

## <a name="simple-url-scope"></a>Étendue d’URL simple

Vous pouvez configurer les URL simples de sorte que leur étendue soit globale mais vous pouvez également spécifier des URL simples différentes pour chaque site central dans votre organisation. Si une URL simple globale et une URL simple de site sont spécifiées, l’URL simple de site prévaut. 

Dans la plupart des cas, nous vous recommandons de définir des URL simples uniquement au niveau global, afin que l’URL simple Meet d’un utilisateur ne change pas si elles se déplacent d’un site à un autre. L’exception serait que les organisations doivent utiliser des numéros de téléphone différents pour les utilisateurs de connexion sur différents sites. Notez que si vous définissez une URL simple (telle que l’URL simple dial-in) sur un site comme URL simple au niveau du site, vous devez également définir les autres URL simples sur ce site pour qu’elles soient également au niveau du site.

Vous pouvez définir des URL simples globales dans le Générateur de topologies. Pour définir une URL simple au niveau du site, utilisez Set-CsSimpleURLConfiguration cmdlet.

La définition d’une URL simple nécessite également la définition d’un enregistrement A et/ou AAAA dans votre configuration DNS.

## <a name="simple-url-naming-and-validation-rules"></a>Règles de validation et d’attribution de noms d’URL simples
<a name="BK_Valid"> </a>

Le Générateur de topologie et les cmdlets Skype Entreprise Server Management Shell appliquent plusieurs règles de validation pour vos URL simples. Vous devez définir des URL simples pour les réunions et l’accès, et éventuellement une URL pour l’administration. Chaque domaine SIP doit avoir une URL simple de réunion mais une seule URL simple est nécessaire pour l’accès et une seule pour l’administration dans toute l’organisation.

Chaque URL simple de votre organisation doit avoir un nom unique et ne peut pas être un préfixe d’une autre URL simple (par exemple, vous n’avez pas pu définir SfB2015.contoso.com/Meet comme URL simple meet et SfB2015.contoso.com/Meet/Dialin comme URL simple Dialin). Les noms d’URL simples ne peuvent pas contenir le nom de domaine complète de l’un de vos pools, ni aucune information de port (par exemple, https://FQDN:88/meet n’est pas autorisée). Toutes les URL simples doivent commencer par https:// préfixe. 

Les URL simples peuvent uniquement contenir des caractères alphanumériques, c’est-à-dire a-z, A-Z, 0-9 et le point (.). Si vous utilisez d’autres caractères, les URL simples peuvent ne pas fonctionner comme prévu.

## <a name="changing-simple-urls-after-deployment"></a>Modification des URL simples après le déploiement
<a name="BK_Valid"> </a>

Si vous modifiez une URL simple après le déploiement initial, vous devez connaître l’impact de la modification sur vos enregistrements et certificats DNS pour les URL simples. Si la base d’une URL simple change, vous devez également modifier les enregistrements et les certificats DNS. Par exemple, si vous changez l’URL de base de SfB2015.contoso.com en meet.contoso.com, vous devez modifier les enregistrements et les https://SfB2015.contoso.com/Meet certificats DNS pour faire référence https://meet.contoso.com à meet.contoso.com. Si vous avez modifié l’URL simple de , l’URL de base de SfB2015.contoso.com reste la même, de sorte qu’aucune modification de DNS ou de certificat https://SfB2015.contoso.com/Meet https://SfB2015.contoso.com/Meetings n’est nécessaire.

Toutefois, chaque fois que vous modifiez un nom d’URL simple, vous devez exécuter **Enable-CsComputer** sur chaque directeur et serveur frontal pour enregistrer la modification.

## <a name="naming-examples-for-simple-urls"></a>Exemples d’attribution de noms pour les URL simples
<a name="BK_Valid"> </a>

Il existe trois options recommandées pour nommer les URL simples. L’option que vous choisissez influe sur la configuration des enregistrements et des certificats DNS A qui prennent en charge les URL simples. Dans chaque option, vous devez configurer une URL simple de réunion pour chaque domaine SIP dans votre organisation. 

Dans votre organisation, une seule URL simple est nécessaire pour l’accès et une seule pour l’administration, quel que soit le nombre de domaines dont vous disposez.

Dans l’option 1, vous devez créer un nom de domaine SIP pour chaque URL simple.

Si vous utilisez cette option, vous devez prévoir un enregistrement DNS A distinct pour chaque URL simple et chaque URL simple de réunion doit être nommée dans les certificats.

**Option 1 de dénomination d’URL simple**


| **URL simple** <br/> | **Exemple** <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | https://meet.contoso.com, https://meet.fabrikam.com et ainsi de suite (un pour chaque domaine SIP de votre organisation)  <br/> |
| Numérotation  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| Administrateur  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

Avec l’option 2, les URL simples sont basées sur le nom de SfB2015.contoso.com. Par conséquent, vous n’avez besoin que d’un seul enregistrement DNS A pour les trois types d’URL simple. Cet enregistrement DNS A fait référence à SfB2015.contoso.com. Mais vous avez quand même besoin d’enregistrements DNS A distincts pour les autres domaines SIP dans votre organisation. 

**Option 2 de dénomination d’URL simple**


| **URL simple** <br/> | **Exemple** <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meet et ainsi de suite (un pour chaque domaine SIP de votre organisation)  <br/> |
| Numérotation  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| Administrateur  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

L’option 3 est particulièrement utile si vous disposez de plusieurs domaines SIP et si vous souhaitez qu’ils aient des URL simples de réunion distinctes mais souhaitez minimiser les enregistrements et les certificats DNS requis pour ces URL simples. 

**Option 3 de dénomination d’URL simple**


| **URL simple** <br/> | **Exemple** <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| Numérotation  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| Administrateur  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a>Option de récupération d’urgence pour les URL simples
<a name="BK_Valid"> </a>

Si vous avez plusieurs sites qui contiennent des pools frontaux et que votre fournisseur DNS prend en charge GeoDNS, vous pouvez configurer vos enregistrements DNS pour les URL simples afin de prendre en charge la récupération d’urgence, de sorte que la fonctionnalité d’URL simple continue même si l’intégralité d’un pool frontal est en panne. Cette fonctionnalité de récupération d’urgence prend en charge les URL simples Meet et Dial-In.

Pour configurer cette option, créez deux adresses GeoDNS. Chacune d’elles comprend deux enregistrements DNS A ou CNAME qui aboutissent à deux pools couplés à des fins de récupération d’urgence. Une adresse GeoDNS est utilisée pour l’accès interne et aboutit au nom de domaine complet web interne ou à l’adresse IP d’équilibrage de charge des deux pools. L’autre adresse GeoDNS est utilisée pour l’accès externe et aboutit au nom de domaine complet web externe ou à l’adresse IP d’équilibrage de charge des deux pools. L’exemple ci-dessous s’applique à l’URL simple Meet et utilise les noms de domaine complets des pools. 

```console
Meet-int.geolb.contoso.com
     Pool1InternalWebFQDN.contoso.com
     Pool2InternalWebFQDN.contoso.com
```

```console
Meet-ext.geolb.contoso.com
     Pool1ExternalWebFQDN.contoso.com
     Pool2ExternalWebFQDN.contoso.com
```

Créez ensuite des enregistrements CNAME qui font aboutir l’URL simple Meet (telles que meet.contoso.com) aux deux adresses GeoDNS.

> [!NOTE]
> Si votre réseau utilise le hairpinning (routage de l’ensemble du trafic de l’URL simple via le lien externe, y compris le trafic en provenance de votre organisation), vous pouvez simplement configurer l’adresse GeoDNS externe et faire aboutir votre adresse URL simple Meet uniquement à cette adresse externe.

Lorsque vous utilisez cette méthode, vous pouvez configurer chaque adresse GeoDNS de façon à distribuer les demandes aux deux pools selon la méthode du tourniquet (round robin), ou bien vous connecter principalement à un pool (par exemple, le pool le plus proche géographiquement) et utiliser l’autre pool seulement en cas de problème de connectivité. 

Vous pouvez définir la même configuration pour l’URL simple Dial-In. Pour ce faire, créez des enregistrements supplémentaires comme ceux de l’exemple précédent, en les remplaçant dans les enregistrements  `dialin` `meet` DNS. Pour l’URL simple Admin, utilisez l’une des trois options mentionnées plus haut dans cette section.

Après avoir défini cette configuration, vous devez utiliser une application de surveillance pour configurer la recherche de défaillance via la surveillance HTTP. Pour l’accès externe, surveillez pour vous assurer que HTTPS GET lyncdiscover.<sipdomain> les demandes au FQDN web externe ou à l’adresse IP de l’équilibreur de charge pour les deux pools sont réussies. Par exemple, les demandes suivantes ne doivent pas contenir d’en-tête **ACCEPT** et doivent retourner **200 OK**.

```console
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

Pour l’accès interne, vous devez surveiller le port 5061 sur le nom de domaine complet web interne ou l’adresse IP d’équilibrage de charge pour les deux pools. Si des défaillances de connectivité sont détectées, l’vip de ces pools doit fermer les ports 80, 443 et 4443.


