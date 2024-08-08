
    This function block concatenates strings and variables of various types.
    The concatenated result is stored in an internal buffer which can be retrieved
    using the GetString method. The buffer can be cleared using the Clear method.

    METHODS:
        L(part : STRING) : FB_Concater
            Adds a static string to the buffer.

        V(part : ANY) : FB_Concater
            Adds a variable of any type to the buffer after converting it to a string.

        GetString() : STRING
            Returns the concatenated string stored in the buffer.

        Clear() : FB_Concater
            Clears the buffer.

    PRIVATE METHODS:
        ConvertAnyToString(part : ANY, result : REFERENCE TO STRING) : HRESULT
            Converts a variable of any type to a string.

    EXAMPLE USAGE:
        VAR
            Concater : FB_Concater;
            topic : STRING;
            deviceId : STRING := 'device123';
            sensorType : STRING := 'temperature';
            valueType : STRING := 'reading';
            sensorId : INT := 1;
        END_VAR

        // Building an MQTT topic dynamically
        Concater.Clear().S('home/').V(deviceId).S('/').V(sensorType).S('/').V(sensorId).S('/').V(valueType);
        topic := Concater.GetString();
        // 'topic' will contain: "home/device123/temperature/1/reading"

        // Another example with different values
        Concater.Clear().S('building/').S('office/').V(deviceId).S('/').S('humidity/').V(sensorId).S('/').S('status');
        topic := Concater.GetString();
        // 'topic' will contain: "building/office/device123/humidity/1/status"
