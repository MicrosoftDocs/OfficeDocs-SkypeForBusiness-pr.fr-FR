---
title: "Attr. d’un certif. d’auth. de serveur à serveur à Microsoft Lync Server 2013"
TOCtitle: "Attr. d’un certif. d’auth. de serveur à serveur à Microsoft Lync Server 2013"
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205253(v=OCS.15)
ms:contentKeyID: 49298793
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Attribution d’un certificat d’authentification de serveur à serveur à Microsoft Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-10-24_

Pour déterminer si un certificat d’authentification de serveur à serveur a été affecté à Microsoft Lync Server 2013, exécutez la commande suivante à partir de Lync Server 2013 Management Shell :

    Get-CsCertificate -Type OAuthTokenIssuer

Si aucune information de certificat n’est retournée, vous devez affecter un certificat de l’émetteur de jeton pour pouvoir utiliser l’authentification de serveur à serveur. En règle générale, n’importe quel certificat Lync Server 2013 peut être utilisé comme certificat OAuthTokenIssuer. Par exemple, votre certificat par défaut Lync Server 2013 peut aussi servir de certificat OAuthTokenIssuer. (Le certificat OAUthTokenIssuer peut aussi correspondre à n’importe quel certificat de serveur web qui inclut le nom de votre domaine SIP dans le champ Objet.) Les deux principales exigences pour le certificat utilisé pour l’authentification de serveur à serveur sont les suivantes : 1) le même certificat doit être configuré comme certificat OAuthTokenIssuer sur tous vos serveurs frontaux, et, 2) le certificat doit être au moins de 2 048 bits.

Si vous n’avez pas de certificat à même de servir pour l’authentification de serveur à serveur, vous pouvez obtenir un nouveau certificat, l’importer, puis l’utiliser pour l’authentification de serveur à serveur. Après avoir demandé et obtenu le nouveau certificat, vous pouvez ensuite ouvrir une session sur l’un de vos serveurs frontaux et passer par une commande Windows PowerShell semblable à celle-ci pour importer et affecter le certificat :

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

Dans la commande précédente, le paramètre Path représente le chemin d’accès complet au fichier du certificat et le paramètre Password correspond au mot de passe ayant été affecté au certificat. Cette procédure ne doit être suivie qu’une seule fois : le service de réplication de Lync Server crée ensuite automatiquement un ensemble de tâches planifiées qui doivent déchiffrer et déployer le certificat sur tous vos serveurs frontaux.

Une autre solution consiste à utiliser un certificat existant comme certificat pour votre authentification de serveur à serveur. (Comme indiqué avant, le certificat par défaut peut être utilisé comme certificat d’authentification de serveur à serveur.) Les deux commandes Windows PowerShell suivantes récupèrent la valeur de la propriété Thumbprint du certificat par défaut, puis utilise la valeur pour faire du certificat par défaut le certificat d’authentification de serveur à serveur :

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

Dans la commande précédente, le certificat récupéré est configuré pour fonctionner comme certificat global d’authentification de serveur à serveur, c’est-à-dire que le certificat est répliqué sur, et utilisé par, tous vos serveurs frontaux. Là encore, cette commande ne doit être exécutée qu’une seule fois et seulement sur l’un de vos serveurs frontaux. Bien que tous les serveurs frontaux doivent utiliser le même certificat, ne configurez pas le certificat OAuthTokenIssuer sur chacun des serveurs frontaux. Configurez-le plutôt une fois, puis laissez le serveur de réplication de Lync Server s’occuper de la copie du certificat sur chaque serveur.

L’applet de commande Set-CsCertificate configure immédiatement le certificat en question pour remplir le rôle de certificat OAuthTokenIssuer actif. (Lync Server 2013 garde deux copies d’un type de certificat : le certificat actif et le certificat précédent.) Si vous avez besoin que le nouveau certificat commence immédiatement à servir de certificat OAuthTokenIssuer, vous devriez alors utiliser l’applet de commande Set-CsCertificate.

Vous pouvez aussi passer par l’applet de commande Set-CsCertificate pour « transmettre » un nouveau certificat. « Transmettre » un certificat revient simplement à configurer un nouveau certificat pour qu’il devienne le certificat OAuthTokenIssuer actif à un moment précis. Par exemple, la commande suivante récupère le certificat par défaut puis le configure pour prendre la suite en tant que certificat OAuthTokenIssuer actif à partir du 1er juillet 2012 :

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

Le 1er juillet 2012, le nouveau certificat est alors configuré comme certificat OAuthTokenIssuer actif et « l’ancien » certificat OAuthTokenIssuer est configuré en tant que certificat précédent.

Si vous ne voulez pas utiliser Windows PowerShell, vous pouvez aussi faire appel à la console MMC Certificats pour exporter un certificat d’un serveur frontal puis l’importer sur tous vos autres serveurs frontaux. Assurez-vous dans ce cas d’exporter la clé privée en plus du certificat même.

> [!CAUTION]  
> Dans ce cas, vous devez effectuer la procédure sur chaque serveur frontal. Pendant l’exportation et l’importation des certificats de cette manière, Lync Server 2013 ne réplique pas le certificat sur chaque serveur frontal.


Quand le certificat est importé sur tous vos serveurs frontaux, il peut ensuite être affecté à l’aide de l’Assistant Déploiement de Lync Server au lieu de Windows PowerShell. Pour affecter un certificat par le biais de l’Assistant Déploiement, effectuez les étapes suivantes sur un ordinateur où l’Assistant est installé :

1.  Cliquez successivement sur Démarrer, Tous les programmes, **Microsoft Lync Server 2013** et **Assistant Déploiement de Lync Server**.

2.  Dans l’Assistant Déploiement, cliquez sur **Installer ou mettre à jour le système Lync Server**.

3.  Dans la page Microsoft Lync Server 2013, cliquez sur le bouton **Exécuter** sous l’en-tête **Étape 3 : Demander, installer ou assigner des certificats**. (Remarque : si vous avez déjà installé des certificats sur cet ordinateur, le bouton **Exécuter** s’appelle **Réexécuter**.)

4.  Dans l’Assistant Certificat, sélectionnez le certificat **OAuthTokenIssuer**, puis cliquez sur **Affecter**.

5.  Dans l’Assistant Assignation de certificat, dans la page **Assignation de certificat**, cliquez sur **Suivant**.

6.  Dans la page **Magasin de certificats**, sélectionnez le certificat à utiliser pour l’authentification de serveur à serveur, puis cliquez sur **Suivant**.

7.  Dans la page Résumé de l’affectation du certificat, cliquez sur **Suivant**.

8.  Dans la page Exécution de commandes, cliquez sur **Terminer**.

9.  Fermez l’Assistant Certificat et l’Assistant Déploiement.

