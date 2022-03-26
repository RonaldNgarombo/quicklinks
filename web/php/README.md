# Linking a php version via the terminal
echo 'export PATH="/opt/homebrew/opt/php@7.4/bin:$PATH"' >> ~/.zshrc
###
echo 'export PATH="/opt/homebrew/opt/php@7.4/sbin:$PATH"' >> ~/.zshrc

Note: php@7.4 is the version which changes depending

# For compilers to find php@7.4 you may need to set:
export LDFLAGS="-L/opt/homebrew/opt/php@7.4/lib"
###
export CPPFLAGS="-I/opt/homebrew/opt/php@7.4/include"

# Calculating Distance Between Two coordinates

## The Great Circle Distance using Haversine Formula

#### Method 1

function haversineGreatCircleDistance($latitudeFrom, $longitudeFrom, $latitudeTo, $longitudeTo,$earthRadius = 6371) {
    // convert from degrees to radians
    $latFrom = deg2rad($latitudeFrom);
    $lonFrom = deg2rad($longitudeFrom);
    $latTo = deg2rad($latitudeTo);
    $lonTo = deg2rad(\$longitudeTo);

    $latDelta = $latTo - $latFrom;
    $lonDelta = $lonTo - $lonFrom;

    $angle = 2 * asin(sqrt(pow(sin($latDelta / 2), 2) + cos($latFrom) * cos($latTo) * pow(sin($lonDelta / 2), 2)));

    return round($angle * $earthRadius);

}

#### Method 2

function getDistance($latitude1, $longitude1, $latitude2, $longitude2)
{
\$earth_radius = 6371;

    // convert from degrees to radians
    $dLat = deg2rad($latitude2 - $latitude1);
    $dLon = deg2rad($longitude2 - $longitude1);

    $a = sin($dLat / 2) * sin($dLat / 2) + cos(deg2rad($latitude1)) * cos(deg2rad($latitude2)) * sin($dLon / 2) * sin($dLon / 2);
    $c = 2 * asin(sqrt($a));
    $d = $earth_radius * $c;

    return round($d);

}

## Install Laravel On Digital Ocean - LAMP using git

https://webdevmatics.com/blog/deploy-laravel-with-digital-ocean
