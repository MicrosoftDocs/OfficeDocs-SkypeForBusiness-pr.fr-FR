---
title: Configuration DNS requise pour simples URL dans Skype pour Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/9/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 'Résumé : Passez en revue les considérations de simples URL dans cette rubrique avant d’implémenter des enregistrements DNS pour Skype pour Business Server 2015.'
ms.openlocfilehash: 87346a7c4c03837e5ebfdf0143cdb7c786f0e43b
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/05/2018
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server-2015"></a>Configuration DNS requise pour simples URL dans Skype pour Business Server 2015
 
**Résumé :** Passez en revue les considérations de simples URL dans cette rubrique avant d’implémenter des enregistrements DNS pour Skype pour Business Server 2015.
  
URL simples facilitent la jointure de réunions pour vos utilisateurs et les rendre plus facile à Skype pour outils d’administration de serveur d’entreprise pour les administrateurs. URL simples utilisent leur propre domaine, ce qui ne doit correspondre à un des domaines SIP que vous définissez. 
  
Skype pour Business Server prend en charge trois URL simples suivantes : respecter, accès à distance et Admin. Il n’est nécessaire pour configurer les URL simples de conférence et d’accès distant, et l’URL d’administration simple est facultative. Les enregistrements système de nom de domaine (DNS) dont vous avez besoin pour prendre en charge d’URL simples dépendent de la façon dont vous avez défini ces URL simple, et si vous souhaitez la prise en charge de la reprise après sinistre pour les URL Simple. 
  
## <a name="simple-url-scope"></a>Étendue d’URL simple

Vous pouvez configurer vos URL simple pour ont une portée globale, ou vous pouvez spécifier une URL simple différentes pour chaque site central de votre organisation. Si une URL simple globale et une URL de site simple sont spécifiés, l’URL du site simple a la priorité. 
  
Dans la plupart des cas, nous vous recommandons de définir une URL simple uniquement au niveau global, afin que les URL de simple respect de l’utilisateur ne change pas s’ils se déplacent d’un site à un autre. L’exception serait des entreprises qui ont besoin d’utiliser des numéros de téléphone pour les utilisateurs d’accès distant sur des sites différents. Notez que si vous définissez une URL simple (par exemple, l’URL simple accès à distance) sur un site à une URL simple au niveau du site, vous devez également définir les autres URL simples sur ce site pour être au niveau du site.
  
Vous pouvez définir des URL simples globales dans le Générateur de topologies. Pour définir une URL simple au niveau du site, utilisez l’applet de commande Set-CsSimpleURLConfiguration.
  
Définition d’une URL simple nécessitera également la définition d’un enregistrement A ou AAAA dans votre configuration DNS.
  
## <a name="simple-url-naming-and-validation-rules"></a>Règles d’affectation de noms et la validation des URL simples
<a name="BK_Valid"> </a>

Générateur de topologies et le Skype pour les applets de commande Business Server Management Shell appliquent plusieurs règles de validation pour vos URL simple. Vous nécessaires à une URL simple pour répondre à et de la numérotation, mais définir une pour l’administration est facultatif. Chaque domaine SIP doit avoir une URL simple respect distincte, mais vous avez besoin qu’un seul appel simple URL et une administration simple pour toute l’organisation.
  
Chaque URL simple dans votre organisation doit avoir un nom unique et ne peut pas être un préfixe d’une autre URL simple (par exemple, vous ne pourriez pas défini SfB2015.contoso.com/Meet comme votre URL simple respect et SfB2015.contoso.com/Meet/Dialin comme votre Dialin simple URL). Les noms d’URL simples ne peut pas contenir le nom de domaine complet d’un de vos pools ou des informations de port (par exemple, https://FQDN:88/meet n’est pas autorisée). Toutes les URL simples doivent commencer par le préfixe https://. 
  
URL simples peuvent contenir uniquement des caractères alphanumériques (c'est-à-dire, d’a à z, A-Z, 0-9 et le point (.). Si vous utilisez d’autres caractères, la simple URL peut ne pas fonctionnent comme prévu.
  
## <a name="changing-simple-urls-after-deployment"></a>Modification Simple URL après le déploiement
<a name="BK_Valid"> </a>

Si vous modifiez une URL simple après le déploiement initial, vous devez être conscient de l’impact de vos enregistrements DNS et les certificats URL simple dans la modification. Si la base d’une simple URL change, vous devez modifier les enregistrements DNS et les certificats ainsi. Par exemple, la modification de https://SfB2015.contoso.com/Meet à https://meet.contoso.com modifie l’URL de base à partir de SfB2015.contoso.com à meet.contoso.com, et vous devez donc modifier les enregistrements DNS et les certificats pour faire référence à meet.contoso.com. Si vous avez modifié l’URL simple à partir de https://SfB2015.contoso.com/Meet à https://SfB2015.contoso.com/Meetings, l’URL de base de SfB2015.contoso.com reste la même, donc aucun DNS ou modifications de certificat sont nécessaires.
  
Toutefois, chaque fois que vous modifiez un simple nom d’URL, vous devez exécuter **CsComputer-activer** sur chaque directeur et le serveur frontal pour enregistrer la modification.
  
## <a name="naming-examples-for-simple-urls"></a>Exemples d’affectation de noms d’URL Simple
<a name="BK_Valid"> </a>

Il existe trois options recommandées pour nommer vos URL simple. L’option que vous choisissez a des implications pour la façon dont vous paramétrez vos enregistrements A DNS et les certificats qui prend en charge les URL simples. Dans chaque option, vous devez configurer une URL simple respect pour chaque domaine SIP de votre organisation. 
  
Vous devez toujours qu’une URL simple dans toute l’organisation pour l’accès à distance et pour administration, quel que soit le nombre de domaines SIP vous avez.
  
Sous Option 1, vous créez un nouveau nom de domaine SIP pour chaque URL simple.
  
Si vous utilisez cette option, vous avez besoin un enregistrement A DNS distinct pour chaque URL simple et chaque URL de simple respect doivent être nommé dans vos certificats.
  
**Option d’attribution de noms URL simple 1**

|**URL simple** <br/> |**Exemple** <br/> |
|:-----|:-----|
|Meet  <br/> |https://meet.contoso.com, https://meet.fabrikam.com, et ainsi de suite (un pour chaque domaine SIP de votre organisation)  <br/> |
|Rendez-vous  <br/> |https://dialin.contoso.com  <br/> |
|Admin  <br/> |https://admin.contoso.com  <br/> |
   
Avec l’Option 2, URL simples sont basés sur le nom de domaine SfB2015.contoso.com. Vous devez donc qu’un seul enregistrement A DNS qui permet à tous les trois types d’URL simples. Cet enregistrement A DNS fait référence à SfB2015.contoso.com. En outre, vous devez toujours les enregistrements A DNS distincts pour les autres domaines SIP de votre organisation. 
  
**Option d’attribution de noms URL simple 2**

|**URL simple** <br/> |**Exemple** <br/> |
|:-----|:-----|
|Meet  <br/> |https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meet, et ainsi de suite (un pour chaque domaine SIP de votre organisation)  <br/> |
|Rendez-vous  <br/> |https://SfB2015.contoso.com/Dialin  <br/> |
|Admin  <br/> |https://SfB2015.contoso.com/Admin  <br/> |
   
L’option 3 est particulièrement utile si vous possédez plusieurs domaines SIP, et si vous voulez qu’ils ont des URL distinctes simples respect, mais pour réduire les exigences DNS de l’enregistrement et le certificat pour ces URL simple. 
  
**Option d’attribution de noms URL simple 3**

|**URL simple** <br/> |**Exemple** <br/> |
|:-----|:-----|
|Meet  <br/> |https://SfB2015.contoso.com/contosoSIPdomain/Meet  <br/> https://SfB2015.contoso.com/fabrikamSIPdomain/Meet  <br/> |
|Rendez-vous  <br/> |https://SfB2015.contoso.com/Dialin  <br/> |
|Admin  <br/> |https://SfB2015.contoso.com/Admin  <br/> |
   
## <a name="disaster-recovery-option-for-simple-urls"></a>Option de récupération d’urgence pour les URL simples
<a name="BK_Valid"> </a>

Si vous disposez de plusieurs sites qui contiennent des pools de Front-End et votre fournisseur DNS prend en charge les GeoDNS, vous pouvez configurer vos enregistrements DNS pour les URL Simple prendre en charge la récupération d’urgence, afin que la fonctionnalité d’URL Simple se poursuit même si un pool frontal entier tombe en panne. Cette fonctionnalité de récupération après sinistre prend en charge la conférence et des URL de simple Dial-In.
  
Pour configurer cette option, créez deux adresses GeoDNS. Chacune d’elles comprend deux enregistrements DNS A ou CNAME qui aboutissent à deux pools couplés à des fins de récupération d’urgence. Une adresse GeoDNS est utilisée pour l’accès interne et aboutit au nom de domaine complet web interne ou à l’adresse IP d’équilibrage de charge des deux pools. L’autre adresse GeoDNS est utilisée pour l’accès externe et aboutit au nom de domaine complet web externe ou à l’adresse IP d’équilibrage de charge des deux pools. L’exemple ci-dessous s’applique à l’URL simple Meet et utilise les noms de domaine complets des pools. 
  
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

Créez ensuite des enregistrements CNAME qui font aboutir l’URL simple Meet (telles que meet.contoso.com) aux deux adresses GeoDNS.
  
> [!NOTE]
> Si votre réseau utilise hairpinning (routage votre URL Simple trafic via le lien externe, y compris le trafic qui provient de votre organisation), puis vous pouvez juste configurer l’adresse externe de la GeoDNS et résoudre votre URL simple respect qu’en adresse externe.
  
Lorsque vous utilisez cette méthode, vous pouvez configurer chaque adresse GeoDNS de façon à distribuer les demandes aux deux pools selon la méthode du tourniquet (round robin), ou bien vous connecter principalement à un pool (par exemple, le pool le plus proche géographiquement) et utiliser l’autre pool seulement en cas de problème de connectivité. 
  
Vous pouvez définir la même configuration pour l’URL simple Dial-In. Pour ce faire, créer des enregistrements supplémentaires tels que ceux de l’exemple précédent, en remplaçant `dialin` de `meet` dans les enregistrements DNS. Pour l’URL simple Admin, utilisez l’une des trois options mentionnées plus haut dans cette section.
  
Après avoir défini cette configuration, vous devez utiliser une application de surveillance pour configurer la recherche de défaillance via la surveillance HTTP. Pour l’accès externe, moniteur afin de vous assurer que lyncdiscover obtenir de HTTPS.<sipdomain> les requêtes sur le web externe, nom de domaine complet ou de charge équilibrage adresse IP les deux pools sont réussies. Par exemple, les requêtes suivantes ne doivent pas contenir n’importe quel en-tête **ACCEPT** et doit retourner **200 OK**.
  
```
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

Pour l’accès interne, vous devez surveiller le port 5061 sur le nom de domaine complet web interne ou l’adresse IP d’équilibrage de charge pour les deux pools. Si des problèmes de connectivité sont détectés, l’adresse IP virtuelle de ces deux pools doit fermer les ports 80, 443 et 4443.
  

