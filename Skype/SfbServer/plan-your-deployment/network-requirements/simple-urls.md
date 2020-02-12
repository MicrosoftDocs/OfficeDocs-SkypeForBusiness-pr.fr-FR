---
title: Configuration DNS requise pour les URL simples dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 'Résumé : passez en revue les remarques relatives aux URL simples de cette rubrique avant d’implémenter les enregistrements DNS pour Skype entreprise Server.'
ms.openlocfilehash: 3296e3678d1d38f021b792a2362f61de66796d0f
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888473"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a>Configuration DNS requise pour les URL simples dans Skype entreprise Server

**Résumé :** Pour plus d’informations sur l’implémentation d’enregistrements DNS pour Skype entreprise Server, consultez les remarques d’URL simples.

Les URL simples simplifient la participation à des réunions pour vos utilisateurs et permettent d’accéder plus facilement aux outils d’administration de Skype entreprise Server aux administrateurs. Les URL simples utilisent leur propre domaine, qui ne doit pas correspondre aux domaines SIP que vous définissez. 

Skype entreprise Server prend en charge les trois URL simples suivantes : réunion, accès et administration. Vous devez configurer des URL simples pour la réunion et le rendez-vous, et l’URL simple d’administration est facultative. Les enregistrements DNS (Domain Name System) nécessaires à la prise en charge d’URL simples dépendent de la façon dont vous avez défini ces URL simples et de la prise en charge de la reprise après sinistre pour des URL simples. 

## <a name="simple-url-scope"></a>Étendue d’URL simple

Vous pouvez configurer vos URL simples pour qu’elles aient une étendue globale ou spécifier différentes URL simples pour chaque site central de votre organisation. S’il s’agit d’une URL simple globale et d’une URL simple de site, l’URL du site est prioritaire. 

Dans la plupart des cas, nous vous conseillons de définir des URL simples uniquement au niveau global, de telle sorte que l’URL de la réunion n’est pas la même que celle d’un site à l’autre. Il peut s’agir d’organisations qui ont besoin d’utiliser différents numéros de téléphone pour les utilisateurs rendez-vous sur différents sites. Notez que si vous définissez une URL simple (par exemple, l’URL d’accès à la Conférence rendez-vous) sur un site, vous devez également définir d’autres URL simples sur ce site comme niveau de site.

Vous pouvez définir des URL simples globales dans le générateur de topologie. Pour définir une URL simple au niveau du site, utilisez l’applet de cmdlet Set-CsSimpleURLConfiguration.

La définition d’une URL simple nécessite également la définition d’un enregistrement A et/ou AAAA dans votre configuration DNS.

## <a name="simple-url-naming-and-validation-rules"></a>Règles de validation et d’attribution d’URL simples
<a name="BK_Valid"> </a>

Le générateur de topologie et les applets de contrôle de l’interpréteur de gestion de Skype entreprise Server appliquent plusieurs règles de validation pour vos URL simples. Vous devez définir des URL simples pour la réunion et le numéro de téléphone, mais la définition d’une pour l’administrateur est facultative. Chaque domaine SIP doit être doté d’une URL simple de connexion, mais vous n’avez besoin que d’une seule URL de composition unique et d’une URL simple d’administration pour l’ensemble de votre organisation.

Chaque URL simple de votre organisation doit avoir un nom unique et ne peut pas être un préfixe d’une autre URL simple (par exemple, vous n’avez pas pu définir SfB2015.contoso.com/Meet comme URL simple de la Conférence). Les noms d’URL simples ne peuvent pas contenir le nom de domaine complet de l’un de vos groupes, https://FQDN:88/meet ni aucune information de port (par exemple, n’est pas autorisée). Toutes les URL simples doivent commencer par le préfixe https://. 

Les URL simples peuvent contenir des caractères alphanumériques (c’est-à-dire, a-z, A-Z, 0-9 et le point (.). Si vous utilisez d’autres caractères, les URL simples risquent de ne pas fonctionner comme prévu.

## <a name="changing-simple-urls-after-deployment"></a>Modification d’URL simples après le déploiement
<a name="BK_Valid"> </a>

Si vous modifiez une URL simple après le déploiement initial, vous devez tenir compte de la façon dont le changement a un impact sur vos enregistrements DNS et les certificats pour les URL simples. Si la base d’une URL simple change, vous devez également modifier les enregistrements DNS et les certificats. Par exemple, si vous https://SfB2015.contoso.com/Meet modifiez https://meet.contoso.com l’URL de base de SfB2015.contoso.com à Meet.contoso.com, vous devez modifier les enregistrements DNS et les certificats pour faire référence à Meet.contoso.com. Si vous avez changé l’URL simple https://SfB2015.contoso.com/Meet de https://SfB2015.contoso.com/Meetingsà, l’url de base de SfB2015.contoso.com reste inchangée et aucune modification du DNS ou du certificat n’est nécessaire.

Néanmoins, chaque fois que vous modifiez un nom d’URL simple, vous devez exécuter **Enable-CsComputer** sur chaque réalisateur et serveur frontal pour enregistrer la modification.

## <a name="naming-examples-for-simple-urls"></a>Exemples d’appellation pour les URL simples
<a name="BK_Valid"> </a>

Il existe trois options recommandées pour nommer vos URL simples. L’option que vous choisissez a des implications sur la configuration de vos enregistrements DNS A et des certificats qui prennent en charge des URL simples. Dans chaque option, vous devez configurer une seule URL de la réunion pour chaque domaine SIP de votre organisation. 

Vous avez toujours besoin d’une seule URL dans l’ensemble de votre organisation pour le rendez-vous, et l’autre pour l’administrateur, quel que soit le nombre de domaines SIP.

Dans l’option 1, vous créez un nouveau nom de domaine SIP pour chaque URL simple.

Si vous utilisez cette option, vous avez besoin d’un enregistrement DNS A distinct pour chaque URL simple et chaque URL de la réunion doit être nommée dans vos certificats.

**Option de nom d’URL simple 1**


| **URL simple** <br/> | **Exemple** <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| Correspondre  <br/>          | https://meet.contoso.com, https://meet.fabrikam.comet ainsi de suite (un pour chaque domaine SIP de votre organisation)  <br/> |
| Rendez-vous  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| Administrateur  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

Avec l’option 2, les URL simples sont basées sur le nom de domaine SfB2015.contoso.com. Par conséquent, vous avez besoin d’un enregistrement DNS A qui active les trois types d’URL simples. Cet enregistrement DNS A fait référence à SfB2015.contoso.com. Par ailleurs, vous avez encore besoin d’enregistrements DNS A séparés pour d’autres domaines SIP de votre organisation. 

**Option de nom d’URL simple 2**


| **URL simple** <br/> | **Exemple** <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| Correspondre  <br/>          | https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meetet ainsi de suite (un pour chaque domaine SIP de votre organisation)  <br/> |
| Rendez-vous  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| Administrateur  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

L’option 3 est particulièrement utile si vous avez de nombreux domaines SIP et que vous souhaitez qu’ils soient séparés par des URL simples et qu’ils souhaitent limiter les exigences d’enregistrements DNS et de certificats pour ces URL simples. 

**Option de nom d’URL simple 3**


| **URL simple** <br/> | **Exemple** <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| Correspondre  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| Rendez-vous  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| Administrateur  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a>Option de reprise après sinistre pour les URL simples
<a name="BK_Valid"> </a>

Si vous disposez de plusieurs sites et que votre fournisseur DNS prend en charge GeoDNS, vous pouvez configurer vos enregistrements DNS pour des URL simples afin de prendre en charge la reprise après sinistre, afin que la fonctionnalité d’URL n’intervient qu’à la fin de l’exécution d’un pool frontal complet. Cette fonctionnalité de reprise après sinistre prend en charge les URL de la réunion et du rendez-vous simples.

Pour le configurer, créez deux adresses GeoDNS. Chaque adresse possède deux enregistrements DNS A ou CNAMe qui sont résolus en deux regroupements qui sont associés à des fins de récupération par sinistre. Une adresse GeoDNS est utilisée pour l’accès interne et est résolue vers l’adresse IP du nom de domaine complet ou du nom de domaine complet (FQDN) du site Web interne. L’autre adresse GeoDNS est utilisée pour l’accès externe et est résolue sur l’adresse IP de nom de domaine complet ou du nom de domaine complet des deux pools. Voici un exemple de l’URL de la réunion, en utilisant les noms de domaine complets (FQDN) pour les pools. 

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

Ensuite, créez des enregistrements CNAMe qui résolvent votre URL de réunion simple (par exemple, meet.contoso.com) sur les deux adresses GeoDNS.

> [!NOTE]
> Si votre réseau utilise Hairpinning (le routage de tout le trafic d’URL simple par le biais du lien externe, y compris le trafic qui provient de votre organisation), vous pouvez simplement configurer l’adresse GeoDNS externe et résoudre votre URL de réunion simple adresse externe.

Lorsque vous utilisez cette méthode, vous pouvez configurer chaque adresse GeoDNS pour utiliser une méthode de tourniquet circulaire pour distribuer les demandes aux deux pools, ou pour vous connecter principalement à un pool (par exemple, le pool localisé plus près) et utiliser l’autre pool uniquement en cas de échec de connectivité. 

Vous pouvez configurer la même configuration pour l’URL d’accès à la Conférence rendez-vous. Pour ce faire, créez des enregistrements supplémentaires comme ceux de l’exemple précédent, `dialin` `meet` en remplaçant les enregistrements DNS. Pour l’URL simple d’administration, utilisez l’une des trois options indiquées plus haut dans cette section.

Une fois cette configuration configurée, vous devez utiliser une application de surveillance pour configurer la surveillance HTTP et surveiller les échecs. Pour un accès externe, assurez-vous que les lyncdiscover HTTPs sont accessibles.<sipdomain> les demandes d’adresse IP de nom de domaine complet ou d’équilibrage de charge Web externes pour les deux pools sont réussies. Par exemple, les requêtes suivantes ne doivent pas contenir d’en-tête **Accept** et doivent retourner **200 OK**.

```console
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

Pour un accès interne, vous devez surveiller le port 5061 sur l’adresse IP du nom de domaine complet (FQDN) du site Web interne ou du solde de charge des deux pools. Si des échecs de connectivité sont détectés, l’adresse VIP de ces groupes doit fermer les ports 80, 443 et 4443.


