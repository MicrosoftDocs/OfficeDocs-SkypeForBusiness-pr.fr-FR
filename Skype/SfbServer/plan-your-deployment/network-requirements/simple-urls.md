---
title: Enregistrements DNS requis pour les URL simples dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 'Résumé : Passez en revue les considérations d’URL Simple dans cette rubrique avant d’implémenter les enregistrements DNS pour Skype pour Business Server.'
ms.openlocfilehash: 6e62190f19969e635690a68ead4f2c96a32a27c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920235"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a>Enregistrements DNS requis pour les URL simples dans Skype pour Business Server

**Résumé :** Passez en revue les considérations d’URL Simple dans cette rubrique avant d’implémenter les enregistrements DNS pour Skype pour Business Server.

URL simples rejoindre des réunions plus facilement pour vos utilisateurs et aux clin Skype pour les outils d’administration Business Server pour les administrateurs. URL simples utilisent leur propre domaine, qui ne doit correspondre à un des domaines SIP que vous définissez. 

Skype pour Business Server prend en charge trois URL simples suivantes : répondre, de rendez-vous et Admin. Vous sont nécessaires pour configurer des URL simples pour Meet et rendez-vous et l’URL simple Admin est facultative. Les enregistrements de nom de domaine DNS (Domain Name System) dont vous avez besoin pour prendre en charge des URL simples dépendent de la façon dont vous avez défini ces URL simples, et si vous souhaitez prendre en charge de la récupération d’urgence pour les URL simples. 

## <a name="simple-url-scope"></a>Étendue des URL simple

Vous pouvez configurer des URL simples pour que l’étendue globale, ou vous pouvez spécifier des URL simples différentes pour chaque site central dans votre organisation. Si une URL simple globale et une URL simple site sont spécifiés, l’URL du site simple est prioritaire. 

Dans la plupart des cas, nous vous recommandons de définir une URL simple uniquement au niveau global, afin que les URL simple de réunion d’un utilisateur ne change pas s’ils se déplacent d’un site vers un autre. L’exception serait organisations ayant besoin d’utiliser des numéros de téléphone pour les utilisateurs entrant sur différents sites. Notez que si vous définissez une URL simple (telles que l’URL simple Dial-in) sur un site à une URL simple au niveau du site, vous devez également définir l’autre URL simples sur le site soit au niveau du site ainsi.

Vous pouvez définir des URL simples globales dans le Générateur de topologie. Pour définir une URL simple au niveau du site, utilisez l’applet de commande Set-CsSimpleURLConfiguration.

Définition d’une URL simple également nécessite la définition d’un enregistrement A ou AAAA dans votre configuration DNS.

## <a name="simple-url-naming-and-validation-rules"></a>Règles d’affectation de noms et la validation des URL simples
<a name="BK_Valid"> </a>

Le Générateur de topologie et la Skype pour les applets de commande Business Server Management Shell pour appliquent plusieurs règles de validation pour votre URL simples. Vous devez définir des URL simples pour Meet et Dialin, mais la définition de l’autre pour l’administration est facultatif. Chaque domaine SIP doit avoir une URL simple Meet distincte, mais vous avez besoin qu’une seule URL simple Dialin et une URL simple Admin pour toute l’organisation.

Chaque URL simple dans votre organisation doit avoir un nom unique et ne peut pas être un préfixe d’une autre URL simple (par exemple, vous ne pourriez pas définir SfB2015.contoso.com/Meet en tant que l’URL simple Meet et SfB2015.contoso.com/Meet/Dialin en tant que votre URL simple Dialin). Noms d’URL simples ne peut pas contenir le nom de domaine complet d’un de vos pools, ou les informations de port (par exemple, https://FQDN:88/meet n’est pas autorisée). Toutes les URL simples doivent commencer par le préfixe https://. 

URL simples peuvent contenir uniquement des caractères alphanumériques (autrement dit, a-z, A-Z, 0-9 et le point (.). Si vous utilisez d’autres caractères, simple URL peut ne pas fonctionnent comme prévu.

## <a name="changing-simple-urls-after-deployment"></a>Modification des URL simples après le déploiement
<a name="BK_Valid"> </a>

Si vous modifiez une URL simple après le déploiement initial, vous devez être conscient de la modification de l’impact de vos enregistrements DNS et les certificats pour les URL simples. Si la base d’une URL simple change, vous devez modifier les enregistrements DNS et les certificats ainsi. Par exemple, en remplaçant https://SfB2015.contoso.com/Meet à https://meet.contoso.com modifie l’URL de base à partir de SfB2015.contoso.com à meet.contoso.com, et vous devez donc modifier les enregistrements DNS et les certificats pour faire référence à meet.contoso.com. Si vous avez modifié l’URL simple à partir de https://SfB2015.contoso.com/Meet à https://SfB2015.contoso.com/Meetings, l’URL de base de SfB2015.contoso.com reste identique, donc aucun DNS ou modification de certificat est nécessaires.

Toutefois, chaque fois que vous modifiez un nom d’URL simple, vous devez exécuter **Enable-CsComputer** sur chaque directeur et le serveur frontal pour enregistrer la modification.

## <a name="naming-examples-for-simple-urls"></a>Exemples d’affectation de noms pour les URL simples
<a name="BK_Valid"> </a>

Il existe trois options recommandées pour la dénomination des URL simples. L’option que vous choisissez a des conséquences sur la manière dont vous configurez vos enregistrements DNS A et les certificats qui prend en charge les URL simples. Dans chaque option, vous devez configurer une URL simple Meet pour chaque domaine SIP dans votre organisation. 

Vous devez toujours qu’une seule URL simple dans toute l’organisation pour le rendez-vous et l’autre pour l’administration, quel que soit le nombre de domaines dont vous disposez.

Dans l’Option 1, vous créez un nouveau nom de domaine SIP pour chaque URL simple.

Si vous utilisez cette option, vous devez un enregistrement DNS A distinct pour chaque URL simple et chaque URL simple de réunion doivent être nommée dans vos certificats.

**Option de dénomination d’URL simple 1**


| **URL simple** <br/> | **Exemple** <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| Répondre à  <br/>          | https://meet.contoso.com, https://meet.fabrikam.com, et ainsi de suite (une pour chaque domaine SIP dans votre organisation)  <br/> |
| Rendez-vous  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| Admin  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

Avec l’Option 2, les URL simples sont basées sur le nom de domaine SfB2015.contoso.com. Par conséquent, vous devez uniquement un enregistrement DNS A qui permet les trois types d’URL simples. Cet enregistrement DNS A fait référence à SfB2015.contoso.com. En outre, vous devez toujours les enregistrements DNS A distinct pour les autres domaines SIP de votre organisation. 

**Option de dénomination d’URL simple 2**


| **URL simple** <br/> | **Exemple** <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| Répondre à  <br/>          | https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meet, et ainsi de suite (une pour chaque domaine SIP dans votre organisation)  <br/> |
| Rendez-vous  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| Admin  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

Option 3 est particulièrement utile si vous possédez plusieurs domaines SIP et que vous souhaitez les URL simples Meet distinctes, mais souhaitez minimiser les enregistrements DNS enregistrements et les certificats requis pour ces URL simples. 

**Option de dénomination d’URL simple 3**


| **URL simple** <br/> | **Exemple** <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| Répondre à  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| Rendez-vous  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| Admin  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a>Option de récupération d’urgence pour les URL simples
<a name="BK_Valid"> </a>

Si vous disposez de plusieurs sites qui contiennent des pools frontaux et prend en charge votre fournisseur DNS GeoDNS, vous pouvez configurer vos enregistrements DNS pour les URL simples prendre en charge de la récupération d’urgence, afin que la fonctionnalité d’URL Simple persiste même si un pool frontal entier tombe en panne. Cette fonctionnalité de récupération d’urgence prend en charge les rendez-vous des URL simples Meet.

Pour ce faire, créez deux adresses GeoDNS. Chaque adresse possède deux enregistrements DNS A ou CNAME qui résolvent les deux pools qui sont associées à des fins de récupération d’urgence. Une adresse GeoDNS est utilisée pour l’accès interne et correspond à le web internes nom de domaine complet charge équilibrage adresse IP ou pour les deux pools. L’autre adresse GeoDNS est utilisé pour l’accès externe et résout web externe complet ou charge d’équilibrage adresse IP pour les deux pools. Voici un exemple d’URL simple de réunion, à l’aide des noms de domaines complets pour les pools. 

```
Meet-int.geolb.contoso.com
     Pool1InternalWebFQDN.contoso.com
     Pool2InternalWebFQDN.contoso.com
```

```
Meet-ext.geolb.contoso.com
     Pool1ExternalWebFQDN.contoso.com
     Pool2ExternalWebFQDN.contoso.com
```

Créez ensuite les enregistrements CNAME deux adresses GeoDNS de résoudre l’URL simple Meet (telles que meet.contoso.com).

> [!NOTE]
> Si votre réseau utilise hairpinning (routage tout le trafic votre URL Simple via le lien externe, y compris le trafic provenant de votre organisation), puis vous pouvez simplement configurer l’adresse GeoDNS externe et résoudre l’URL simple Meet uniquement que adresse externe.

Lorsque vous utilisez cette méthode, vous pouvez configurer chaque adresse GeoDNS pour utiliser une méthode de tourniquet (round robin) pour distribuer les demandes pour les deux pools, ou pour se connecter principalement à un pool (par exemple, le pool situé géographiquement plus près) et utiliser le pool d’uniquement en cas de Échec de connectivité. 

Vous pouvez configurer la même configuration de l’URL simple Dial-In. Pour ce faire, créer des enregistrements supplémentaires telles que celles dans l’exemple précédent, en remplaçant `dialin` pour `meet` dans les enregistrements DNS. Pour l’URL simple d’administration, utilisez une des trois options répertoriées plus haut dans cette section.

Une fois cette configuration est configurée, vous devez utiliser une application de surveillance pour configurer la surveillance HTTP pour surveiller les échecs. Pour l’accès externe, moniteur pour vous assurer que lyncdiscover obtenir le protocole HTTPS.<sipdomain> demandes au nom de domaine complet ou charge l’adresse IP d’équilibrage de la pour les deux pools web externe réussissent. Par exemple, les requêtes suivantes ne doit pas comporter n’importe quel en-tête **ACCEPT** et doit retourner **200 OK**.

```
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

Pour l’accès interne, vous devez surveiller le port 5061 sur le site web interne nom de domaine complet ou l’adresse IP les deux pools d’équilibrage de charge. Si les éventuels problèmes de connectivité sont détectées, l’adresse IP virtuelle pour ces pools doit fermer les ports 80, 443 et 4443.


